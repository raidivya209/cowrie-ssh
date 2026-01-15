## Commands Used – Cowrie SSH Honeypot Lab

## Environment Setup
sudo apt update
sudo apt install python3 python3-pip virtualenv git

## Cowrie Installation
git clone https://github.com/cowrie/cowrie.git
cd cowrie
virtualenv cowrie-env
source cowrie-env/bin/activate
pip install -r requirements.txt

## Cowrie Configuration
cp etc/cowrie.cfg.dist etc/cowrie.cfg
nano etc/cowrie.cfg

## Start Cowrie
bin/cowrie start

## Verify Listening Ports
ss -tulnp

## Network Namespace Simulation
sudo ip netns add attacker1
sudo ip netns add attacker2
sudo ip netns add attacker3

sudo ip netns exec attacker1 bash
sudo ip netns exec attacker2 bash
sudo ip netns exec attacker3 bash

## SSH Login Attempts
ssh root@127.0.0.1 -p 2222
ssh root@<honeypot-ip> -p 2222

## Hydra Brute Force Simulation
hydra -l root -P passwords.txt ssh://127.0.0.1:2222
hydra -l admin -P passwords.txt ssh://<honeypot-ip>:2222

## Log Analysis
cd cowrie
cat var/log/cowrie/cowrie.json
jq '.eventid' var/log/cowrie/cowrie.json
jq -r '.src_ip' var/log/cowrie/cowrie.json | sort | uniq -c
jq -r '.username' var/log/cowrie/cowrie.json | sort | uniq -c
jq -r '.password' var/log/cowrie/cowrie.json | sort | uniq -c

## Command Capture Analysis
jq -r 'select(.eventid=="cowrie.command.input") | .input' var/log/cowrie/cowrie.json

## Session Analysis
jq -r 'select(.eventid=="cowrie.session.connect")' var/log/cowrie/cowrie.json
jq -r 'select(.eventid=="cowrie.session.closed")' var/log/cowrie/cowrie.json

## Stop Cowrie
bin/cowrie stop




