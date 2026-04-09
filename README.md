# -Project3  Kubernetes-Monitoring-Stack-using-Helm-Prometheus-Grafana

📌 Overview

This project demonstrates the deployment of a complete monitoring stack on a Kubernetes cluster using Infrastructure as Code (IaC).
Prometheus is used for metrics collection, while Grafana is used for visualization.  
The entire setup is automated using Terraform and Helm for scalability and consistency.


🎯 Key Features

☸️ Kubernetes cluster setup using Minikube

📊 Prometheus for metrics collection

📈 Grafana for visualization

⚙️ Helm charts for deployment

🔄 Real-time monitoring dashboards


  🏗️ Architecture

   +----------------------+
    |  Kubernetes Cluster  |
    +----------------------+
    
            
             |
   -------------------------
    
   |                       |
   v                       v


+----------------+ +----------------+
| Prometheus | | Grafana |
| (Monitoring) | | (Visualization)|

+----------------+ +----------------+




🛠️ Tech Stack

- Kubernetes
  
- Terraform(minikube)
  
- Helm
  
- Prometheus
  
- Grafana

Project Structure

microservices-project/
│

├── user-service/
│   ├── app.py

│   └── Dockerfile
│

├── product-service/

│   ├── app.py

│   └── Dockerfile
│

├── k8s/

│   ├── user-deployment.yaml

│   ├── user-service.yaml

│   ├── product-deployment.yaml

│   ├── product-service.yaml

│   ├── hpa.yaml

│   ├── pv.yaml

│   └── pvc.yaml
│
├
│
└── README.md



⚙️ Implementation Steps

1️⃣ Launch EC2 Instance

Created an Ubuntu EC2 instance on AWS

Connected using SSH

2️⃣ Install Required Tools

Installed Docker

sudo apt install docker-io -y

Installed Minikube

curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-windows-amd64.exe

Installed Kubectl

curl -LO "https://dl.k8s.io/release/v1.30.0/bin/windows/amd64/kubectl.exe"

Installed Helm

curl -LO https://get.helm.sh/helm-v3.14.0-windows-amd64.zip

3️⃣ Start Kubernetes Cluster

Started Minikube cluster

minikube start

4️⃣ Add Helm Repositories

Added Prometheus Helm repo

helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

Added Grafana Helm repo

helm repo add grafana https://grafana.github.io/helm-charts

Updated Helm repositories

helm repo update


<img width="1600" height="848" alt="image" src="https://github.com/user-attachments/assets/ce4e30ae-7d47-412f-90ab-65d4fd0ab562" />


5️⃣ Create Namespace


Created a namespace named monitoring

6️⃣ Deploy Prometheus

Installed Prometheus using Helm

helm install prometheus prometheus-community/prometheus --namespace monitoring --createnamespace

Verified all Prometheus pods are running


7️⃣ Access Prometheus


Used port forwarding to access Prometheus UI


<img width="1600" height="357" alt="image" src="https://github.com/user-attachments/assets/1b18c79e-a34d-40ae-a292-069963e36e08" />


8️⃣ Deploy Grafana


Installed Grafana using Helm


Verified Grafana pod status


<img width="1600" height="637" alt="image" src="https://github.com/user-attachments/assets/8c231413-9a4b-43ed-bdcc-9ed009ad43fb">



9️⃣ Access Grafana


Used port forwarding to access Grafana


Retrieved admin password using Kubernetes secret


Logged into Grafana


🔟 Configure Monitoring


Added Prometheus as a data source in Grafana

<img width="1600" height="808" alt="image" src="https://github.com/user-attachments/assets/846ea7db-bb8e-4a8f-ae4d-08ec179f78a0" />



Imported dashboard (ID: 3000)


<img width="1600" height="795" alt="image" src="https://github.com/user-attachments/assets/0f40ca99-776b-48ff-945b-e11594a06189" />




<img width="1600" height="817" alt="image" src="https://github.com/user-attachments/assets/274d64c6-76ea-42d1-a634-0245f852948a" />





📊 Result

Successfully monitored:

CPU usage

Memory usage

Network traffic

Node metrics



🎯 Conclusion

This project successfully demonstrates how to deploy and configure a Kubernetes monitoring stack using Prometheus and Grafana with Helm, enabling real-time observability of cluster performance.


