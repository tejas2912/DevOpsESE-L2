# Task 10: CI/CD with Kubernetes using Jenkins (App: Student Dashboard)

**Name:** Tejas Lahade  
**PRN:** 505  

---

## 🎯 Objective
To automate the build, test, and deployment process of a Kubernetes-based web application (**Student Dashboard**) using a **Jenkins CI/CD pipeline**.

---

## 🧩 Steps Performed

### **Step 1: Repository Setup**
- Created a GitHub repository named **`k8s-cicd-demo`**.  
- Added files: **`Jenkinsfile`**, **`Dockerfile`**, and **`deployment.yaml`**.  
- Created branches:  
  - `dev` → Testing environment  
  - `main` → Production environment  

---

### **Step 2: Jenkins Configuration**
- Installed necessary plugins: **Git**, **Docker**, **Kubernetes**, and **Pipeline**.  
- Created credentials in Jenkins:  
  - **`github`** → GitHub username + personal access token  
  - **`dockerhub`** → DockerHub username + password  

---

### **Step 3: Pipeline Creation**
- Created a new **Pipeline job** in Jenkins.  
- Linked it with the **GitHub repository (`k8s-cicd-demo`)**.  
- Used the **Jenkinsfile** from the repository to define pipeline stages.  

---

### **Step 4: Jenkinsfile Stages**
1. **Checkout Code** – Clones the latest code from GitHub.  
2. **Build Docker Image** – Builds Docker image for the *Student Dashboard* app.  
3. **Push to DockerHub** – Pushes the built image to DockerHub repository.  
4. **Deploy to Kubernetes** – Applies **deployment.yaml** using `kubectl apply` to deploy the app on **Minikube**.  

---

### **Step 5: Pipeline Execution**
- Executed the pipeline successfully from the Jenkins dashboard.  
- Verified build logs and Kubernetes deployment using:  
  ```bash
  kubectl get pods
  kubectl get svc
