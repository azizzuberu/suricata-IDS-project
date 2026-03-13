# Network Intrusion Detection System using Suricata and EveBox

## Overview
This project demonstrates the deployment of a Network Intrusion Detection System (NIDS) using Suricata and EveBox.  
The system monitors network traffic, detects potential attacks, and visualizes alerts through the EveBox dashboard.

## Technologies Used
- Suricata IDS
- EveBox
- Ubuntu Linux
- Emerging Threats Open Rules
- tcpdump
- jq

## Architecture
Attacker Machine (Kali Linux)
        |
        |  Network Traffic
        v
Victim / Monitoring Machine (Ubuntu + Suricata)
        |
        v
Suricata Analysis Engine
        |
        v
eve.json Alert Logs
        |
        v
EveBox Dashboard (Web Interface)

## Features
- Real-time network traffic monitoring
- Detection using Emerging Threats rule set
- Custom local Suricata rules
- Web-based alert visualization with EveBox
- Attack simulation for testing IDS alerts

## Installation Steps

### Install Suricata
```bash
sudo apt update
sudo apt install suricata

## start suricata
sudo systemctl start suricata

## update suricata rules
sudo suricata-update

## verify suricata configuration

sudo suricata -T -c /etc/suricata/suricata.yaml

## Installing EveBox (Alert Visualization)

EveBox is used to visualize Suricata alerts through a web dashboard.

### Install EveBox
sudo apt install evebox

### Start EveBox Server
sudo evebox server \
--host 0.0.0.0 \
--port 5636 \
--datastore sqlite \
--database /var/lib/evebox/evebox.db \
--input /var/log/suricata/eve.json

### Access the Dashboard
Open your browser and navigate to:

http://localhost:5636
or
http://<your machine server-ip>:5636 if accessing from external machine


Author
Zuberu Abdul Aziz -->> Cybersecurity and Network Defence Enthusiast
