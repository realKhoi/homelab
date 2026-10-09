# homelab
Welcome to my homelab! This repository is meant as a platform for me to document my homelab and share my progress with my fellow githubbers. I started getting into homelabbing during my 2nd year of my bachelors where I got myself a raspberry pi 5. However as you can see I have come quite a bit since then with a 10 inch rack. I built this lab mainly as a platform to experiment and learn IT concepts like IaC (terraform/tofu, Ansible, Kubernetes etc...) and hosting my various projects. So far I have learnt alot when it comes to hardware and virtualization, but I will get more into that further down the documentation.

# Pictures


# Hardware specifications
Mini-PC(PVE1) - Dell Optiplex 3060 Micro
Specification:
  - Processor: Intel I5-8500T 6C/6T
  - Memory: 16GB DDR4 RAM
  - Storage: 512GB NVME, 512GB SATA SSD

Mini-PC(PVE2) - Dell Optiplex 3060 Micro
Specification:
  - Processor: Intel I5-8500T 6C/6T
  - Memory: 16GB DDR4 RAM
  - Storage: 256GB NVME, 256GB SATA SSD

Mini-PC(PVE2) - Dell Optiplex 3060 Micro
Specification:
  - Processor: Intel I5-8500T 6C/6T
  - Memory: 16GB DDR4 RAM
  - Storage: 256GB NVME, 1TB HDD

RaspberryPi 7" display paired with a RPI3B

Netgear GS105 switch

# Services
I am running all 3 machines in a 3 node proxmox cluster. From there I host my services using LxCs or VMs.

PVE1:
  - AdGuard
  - VaultWarden (Password manager)
  - HermesAgent (AI agent)
  - Finn.no-Bot (Website scrubber)
  - Discord-bot
  - Minecraft-server

PVE2: 
  - immich (Photo library)
  - Nginx Proxy Manager (Reverse proxy)
  - Tailscale (VPN)
  - Protfolio-Website (dead)

PVE3: 
  - influxDB
  - Grafana (Monitoring)

# Architecture
 - All machines are running a hypervisor OS called proxmox, where all of them are connected together creating a cluster
 - Tailscale is a mesh VPN provider which I use for remote access to the homelab
 - InfluxDB is used to collect cluster data from proxmox (Storage capacity, CPU usage, memory usage, etc)
 - Grafana is used to display selected data from InfluxDB, for easy monitoring on the screen
 - Most of the services are running on LxC for resource efficiency. Most of them uses Ubuntu with some using Debian.






