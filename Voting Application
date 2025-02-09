# Kubernetes and Docker Project

This project showcases the integration of **Docker** and **Kubernetes** to deploy a multi-component application. It involves containerizing applications, managing them with Kubernetes resources, and version-controlling the project using **Git** and **GitHub**.

## Table of Contents

- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Project Structure](#project-structure)
- [Setup Instructions](#setup-instructions)
- [Kubernetes Resources](#kubernetes-resources)
- [Version Control](#version-control)
- [Future Improvements](#future-improvements)

---

## Project Overview

This project demonstrates:

1. **Docker**: Creating and managing Docker containers with persistent storage.
2. **Kubernetes**: Deploying applications using ConfigMaps, Secrets, Deployments, and Services.
3. **Git & GitHub**: Version-controlling the project and managing deployment histories.
4. **Multi-Component App**: Deploying a voting application with Redis, a worker service, PostgreSQL, and a results display.

---

## Technologies Used

- **Docker**
- **Kubernetes**
- **Nginx**
- **Redis**
- **PostgreSQL**
- **Node.js**
- **Git & GitHub**

---

## Project Structure

```plaintext
.
├── Dockerfile                      # Docker configuration for the app
├── app-config.yaml                 # Kubernetes ConfigMap for environment variables
├── app-secret.yaml                 # Kubernetes Secret for sensitive data
├── jachimike-rollout-history.txt   # Rollout history of Kubernetes deployments
├── postgres-deployment.yaml        # PostgreSQL Deployment configuration
├── redis-deployment.yaml           # Redis Deployment configuration
├── result-app.yaml                 # Results App Deployment
├── result-app-service.yaml         # Results App Service
├── voting-app.yaml                 # Voting App Deployment
├── voting-app-service.yaml         # Voting App Service
├── webapp-deploy.yaml              # Nginx Web App Deployment
├── webapp-service.yaml             # Nginx Web App Service
├── worker-deployment.yaml          # Worker Service Deployment
├── server.js                       # Node.js backend server
├── package.json                    # Node.js dependencies
└── .gitignore                      # Git ignore file
```

---

## Setup Instructions

1. **Clone the Repository:**

```bash
git clone https://github.com/your-username/k8s-and-docker-project.git
cd k8s-and-docker-project
```

2. **Build the Docker Image:**

```bash
docker build -t jachimike-webapp .
```

3. **Run Docker Container with Volume:**

```bash
docker volume create Jachimike_data
docker run -d --name jachimike-webapp -v Jachimike_data:/usr/share/nginx/html -p 8080:80 nginx
```

4. **Deploy Kubernetes Resources:**

Apply the Kubernetes manifests in the following order:

```bash
kubectl apply -f app-config.yaml
kubectl apply -f app-secret.yaml
kubectl apply -f postgres-deployment.yaml
kubectl apply -f redis-deployment.yaml
kubectl apply -f voting-app.yaml
kubectl apply -f voting-app-service.yaml
kubectl apply -f worker-deployment.yaml
kubectl apply -f result-app.yaml
kubectl apply -f result-app-service.yaml
```

5. **Access the Applications:**

For development and testing, the services are configured using NodePort. However, note that in our production environment, firewall rules and network policies are in place to restrict external access to these ports. This ensures that while NodePort is convenient for local testing, the services are only accessible on our private network in production.

- **Voting App**: `http://<node-ip>:31000`
- **Results App**: `http://<node-ip>:31001`
- **Web App (Nginx)**: `http://<node-ip>:8080`

---

## Kubernetes Resources

- **ConfigMap**: Stores environment configurations.
- **Secret**: Secures sensitive credentials like database passwords.
- **Deployment**: Manages application deployment and scaling.
- **Service**: Exposes the applications to be accessible externally.

---

## Version Control

- All code changes and deployment updates are tracked using **Git**.
- Rollout history is documented in `jachimike-rollout-history.txt`.
- Repository hosted on [GitHub](https://github.com/jachiwayne/k8s-and-docker-project).

---

## Future Improvements

- Implement **CI/CD pipelines** for automated deployments.
- Add **monitoring tools** like Prometheus and Grafana.
- Incorporate **unit tests** and **integration tests** for robust development.

---

## License

This project is open for public use and does not have a specific license attached. Feel free to use, modify, and share it freely.

---

**Author:** Jachimike  
**LinkedIn:** www.linkedin.com/in/jachimike-onwuchekwa-61029017b

