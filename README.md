# Nginx Deployment using Docker and Kubernetes

This project demonstrates the deployment of an Nginx web server using Docker and Kubernetes. It includes Kubernetes manifests for creating deployments and services while utilizing Docker for containerization.

## Project Structure
```
nginx-deployment/
├── Dockerfile
├── index.html
└── k8s-manifests/
    ├── deployment.yaml
    ├── service.yaml
    └── configmap.yaml
```

## Prerequisites
- Docker
- Kubernetes (Minikube or Kind recommended)
- Kubectl CLI
- Git
- Terraform (if using infrastructure automation)

---

## Installation and Setup

### Step 1: Clone the Repository
```bash
git clone https://github.com/y7ksh-r/Nginx-Deployment-using-Docker-and-K8s.git
cd Nginx-Deployment-using-Docker-and-K8s
```

### Step 2: Build the Docker Image
```bash
docker build -t my-nginx:latest .
```

### Step 3: Deploy Using Kubernetes
1. Start your Kubernetes cluster:
   ```bash
   kind create cluster --name nginx-cluster
   ```

2. Apply Kubernetes manifests:
   ```bash
   kubectl apply -f k8s-manifests/
   ```

3. Verify the pods are running:
   ```bash
   kubectl get pods
   ```

4. Check services to find the NodePort:
   ```bash
   kubectl get svc
   ```

5. Access the application in your browser using:
```
http://localhost:<NodePort>
```

---

## Key Features
✅ Nginx web server setup with a custom index.html page  
✅ Dockerfile for containerization  
✅ Kubernetes manifests for deployment and service configuration  
✅ Uses NodePort for easy access from localhost  
✅ Demonstrates best practices for containerized application deployment  

---

## Troubleshooting
- **Port Conflict Issue:** If `kubectl port-forward` fails, check for processes occupying the port:
  ```bash
  sudo lsof -i :8080
  sudo kill -9 <PID>
  ```
- **Image Pull Error:** Ensure your Docker image is built locally and the `imagePullPolicy` is set to `Never` in your `deployment.yaml`.

---

## Future Enhancements
- Implement CI/CD pipeline using Jenkins
- Add monitoring with Prometheus and Grafana
- Automate infrastructure setup using Terraform

---

## Contributing
Contributions are welcome! Feel free to fork the repo, create a feature branch, and submit a pull request.

---

## Author
**Yaksh Rajput**  
GitHub: [y7ksh-r](https://github.com/y7ksh-r)

---

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

