# DevsecOpps-Aws-microservice-Netflix
This projects is build and deployed from scratch used aws and k8s docker jenkins and monitoring tools with results

# 🚀 Cloud-Native DevOps Pipeline Project

This project demonstrates a full-stack CI/CD pipeline deployed on AWS EC2 using Jenkins, Docker, SonarQube, Trivy, Prometheus, Grafana, and Kubernetes via ArgoCD. It features a Netflix clone application containerized and deployed with security and monitoring integrations.

---

## 🧱 Architecture Overview

- **Cloud Provider**: AWS EC2 (Ubuntu)
- **CI/CD**: Jenkins
- **Code Quality**: SonarQube
- **Security Scanning**: Trivy
- **Containerization**: Docker
- **Monitoring**: Prometheus + Grafana
- **Deployment**: Kubernetes via ArgoCD

---

## 🔧 Tools & Technologies

| Tool        | Purpose                          |
|-------------|----------------------------------|
| Jenkins     | CI/CD orchestration              |
| Docker      | Containerization                 |
| SonarQube   | Static code analysis             |
| Trivy       | Vulnerability scanning           |
| Prometheus  | Metrics collection               |
| Grafana     | Visualization                    |
| ArgoCD      | GitOps-based K8s deployment      |
| EC2         | Hosting all services             |

---

## 📦 Project Setup

### 1. Launch EC2 Instance
```bash
# Ubuntu EC2 with open ports: 8080 (Jenkins), 9000 (SonarQube), 3000 (Grafana), 9090 (Prometheus)



install docker and run jenkins
sudo apt update
sudo apt install docker.io -y
docker volume create jenkins_data
docker run -d --name jenkins -p 8080:8080 -v jenkins_data:/var/jenkins_home jenkins/jenkins:lts

run sonarqube
docker run -d --name sonarqube -p 9000:9000 sonarqube:latest

install trivy
curl -sfL https://raw.githubusercontent.com/aquasecurity/trivy/main/contrib/install.sh | sudo sh -s -- -b /usr/local/bin

instal grafana
docker run -d --name prometheus -p 9090:9090 prom/prometheus
docker run -d --name grafana -p 3000:3000 grafana/grafana



📈 Monitoring Setup

• Node Exporter installed on EC2
• Prometheus scrapes metrics
• Grafana dashboard visualizes Jenkins, EC2, and container health


---

🧠 Key Learnings

• Integrated CI/CD with security gates and code quality checks
• Optimized EC2 resources under budget constraints
• Solved Jenkins slowness by pruning Docker and limiting container memory
• Built GitOps deployment flow with ArgoCD


---

📸 Architecture Diagram

[Developer]
     |
     v
[GitHub Repo] ---> [Jenkins CI/CD]
     |                  |
     |                  v
     |           [Docker Build]
     |                  |
     v                  v
[SonarQube]       [Trivy Scan]
     |                  |
     v                  v
[Docker Image] --> [ArgoCD] --> [Kubernetes Cluster]
     |
     v
[Prometheus] --> [Grafana Dashboard]

---








