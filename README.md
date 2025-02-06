# 📌 Jenkins Docker Pipeline Lab  

This repository contains a **Jenkins pipeline** that builds and pushes a Docker image from a GitHub repository.  

## 🔗 Related Repository  
For Jenkins deployment on Kubernetes, check:  
➡️ [Jenkins Kubernetes Setup](https://github.com/Hager706/jenkins-k8s-setup)  

---

## 🚀 Setup Steps  

### 1️⃣ Clone the Repository  
```sh
git clone https://github.com/Hager706/jenkins-docker-pipeline-lab.git
cd jenkins-docker-pipeline-lab
```

### 2️⃣ Create a Jenkins Pipeline  
1. Open **Jenkins Dashboard**.  
2. Go to **New Item** → Select **Pipeline** → Name it (e.g., `Docker-Build`).  
3. In the **Pipeline** section:  
   - Select **Pipeline script from SCM**.  
   - Choose **Git** and enter your repository URL:  
     ```
     https://github.com/Hager706/jenkins-docker-pipeline-lab.git
     ```
   - Branch: `main`  
   - Script Path: `Jenkinsfile`  
4. Click **Save**.  

### 3️⃣ Run the Pipeline  
1. Go to **Jenkins Dashboard** → Select your pipeline (`Docker-Build`).  
2. Click **Build Now**.  

### 4️⃣ Check the Build Logs  
- The pipeline will:  
  ✅ Pull the **Dockerfile** from GitHub.  
  ✅ Build the Docker image.  
  ✅ Push the image to Docker Hub.  

---

## 📂 Repository Files  
- **`Jenkinsfile`** → Defines the CI/CD pipeline steps.  
- **`Dockerfile`** → Contains instructions to build the container image.  

---
