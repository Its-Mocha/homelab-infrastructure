# Enterprise Network Monitoring Stack

![Project Status](https://img.shields.io/badge/status-active-success)
![Platform](https://img.shields.io/badge/platform-RHEL%209-red)
![Docker](https://img.shields.io/badge/container-Docker-blue)

## 📋 Overview
This project is a self-hosted network observability solution designed to monitor Service Level Agreements (SLAs) for critical internal infrastructure and external connectivity.

Deployed on a hardened **Red Hat Enterprise Linux 9 (RHEL 9)** node, this stack utilizes **Docker** and **Uptime Kuma** to provide real-time latency tracking, uptime analysis, and status page generation for IT operations.

## 🏗️ Architecture & Tech Stack
* **Host OS:** Red Hat Enterprise Linux 9.5 (Hardened)
* **Container Engine:** Docker CE (Community Edition)
* **Orchestration:** Docker Compose (via Portainer Stacks)
* **Application:** Uptime Kuma (Monitoring & Status Page)
* **DNS:** Integration with local Pi-hole for internal hostname resolution.

## 🚀 Features
* **Real-time Monitoring:** 20-second heartbeat checks for public DNS (8.8.8.8) and local gateways.
* **Internal Service Tracking:** Monitoring of local DNS resolvers (Pi-hole) and virtualization hosts (Proxmox).
* **Public Status Page:** Automated generation of incident reports and system status for end-users.
* **Data Persistence:** Configured with Docker Volumes to ensure historical data survives container rebuilds.

## 🛠️ Deployment

### Prerequisites
* A server running RHEL 9 or Rocky Linux 9.
* Docker Engine and Docker Compose installed.

### Installation (Infrastructure as Code)
This stack is defined as a `docker-compose` service. To deploy:

1.  Clone the repository:
    ```bash
    git clone [https://github.com/Its-Mocha/homelab-infrastructure.git](https://github.com/Its-Mocha/homelab-infrastructure.git)
    cd homelab-infrastructure/uptime-kuma
    ```

2.  Start the container:
    ```bash
    docker compose up -d
    ```

3.  Access the dashboard at `http://<SERVER-IP>:3001`.

## 📸 Screenshots
<img width="1247" height="804" alt="chrome_76gj5J6rUr" src="https://github.com/user-attachments/assets/6cd8f0f2-973b-4762-b93c-989f1bdc507d" />
<img width="1358" height="522" alt="4bkUPrhThf" src="https://github.com/user-attachments/assets/887cf21f-0704-43d2-aa8a-73b93c58671b" />


## 🔮 Future Improvements
* **Alerting:** Integrate Discord/Slack webhooks for instant downtime notifications.
* **Security:** Implement Nginx Reverse Proxy with Let's Encrypt SSL.
* **Automation:** Convert manual deployment to an Ansible Playbook.
