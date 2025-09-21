# Static Website Hosting with AWS CI/CD Pipeline

This project demonstrates how to host a static website on **Amazon S3** with a **CI/CD pipeline** using **AWS CodePipeline**, and how to enhance it with approval workflows and performance optimizations using **CloudFront**.

---

## 🚀 Project Overview

The repository contains a simple HTML file that will be deployed to an S3 bucket via CodePipeline.  

The project has two phases:

1. **Foundational**: Basic static website hosting with automated deployments.  
2. **Advanced**: Adding a manual approval step and optimizing performance with CloudFront.

---

## 📋 Foundational Steps

1. **Repository Setup**  
   - Create a new repository in GitHub.  
   - Add and commit the provided HTML file.  

2. **S3 Bucket Creation**  
   - Create and configure an S3 bucket to host a static website.  
   - Enable **static website hosting** in the bucket properties.  
   - Ensure correct **bucket policy** and **public access settings** for website hosting.  

3. **CI/CD Pipeline with CodePipeline**  
   - Create a new **AWS CodePipeline**.  
   - **Source Stage**: Connect the GitHub/CodeCommit repo as the source.  
   - **Deploy Stage**: Select the S3 bucket as the deployment target.  

4. **Test Deployment**  
   - Deploy the pipeline.  
   - Verify that the static website is accessible from the S3 website endpoint.  

5. **Trigger Workflow**  
   - Commit and push a change to the repo (e.g., update text in the HTML file).  
   - Confirm that the pipeline detects the change and redeploys the updated file.  

---

## ⚡ Advanced Enhancements

1. **Manual Approval Step**  
   - Add a **manual approval action** between the **Build** (if present) and **Deploy** stages.  
   - This approval is completed directly in the **CodePipeline console GUI**.  
   - A senior developer or authorized user logs into the AWS Management Console, navigates to the pipeline, and manually approves or rejects the deployment.  

2. **CloudFront Distribution**  
   - Create a **CloudFront distribution** with the S3 website bucket as the origin.  
   - Update DNS (Route 53 or your DNS provider) to point your domain to the CloudFront distribution for reduced latency and global availability.  

---

## 🛠️ Technologies Used
- **AWS S3** – Static website hosting  
- **AWS CodePipeline** – CI/CD pipeline  
- **AWS CloudFront** – Content delivery and caching  
- **GitHub / CodeCommit** – Source code management  

---

## ✅ Verification Checklist
- [ ] Website is accessible via S3 bucket endpoint.  
- [ ] Changes to repo trigger pipeline deployment.  
- [ ] Manual approval step is in place and performed via the CodePipeline GUI.  
- [ ] Website is served globally with low latency via CloudFront.  

---

## 📂 Repository Structure
```
.
├── index.html   # Main static website file
└── README.md    # Project documentation
```

---

## 📖 Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/<your-repo>.git
   ```
2. Make changes to `index.html`.
3. Commit and push:
   ```bash
   git add .
   git commit -m "Update website content"
   git push origin main
   ```
4. Approve deployment via the **AWS CodePipeline console**.  
5. Access your updated website via CloudFront or S3 endpoint.
