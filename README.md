# Jenkins CI/CD Pipeline for Website Deployment 



<img width="871" alt="Screenshot 2023-12-16 at 2 34 12 PM" src="https://github.com/MasudDevSecOps/Jenkins-Sonarqube-Docker-AWS/assets/118152048/db93db68-ec95-4846-90e3-a72e633a5e87">



## Introduction

This project involved setting up a continuous integration and continuous deployment (CI/CD) pipeline to automate the process of building, testing, and deploying a website using Jenkins, GitHub, SonarQube, Docker, and Amazon Web Services (AWS).

## Architecture

The architecture consists of the following components:

- 3 AWS EC2 Instances hosting:
  - Jenkins server
  - SonarQube server
  - Docker server
- GitHub - Holds source code for the website
- SonarQube - Code quality and test coverage analysis
- Docker - Containerization of the website application
- Jenkins - Orchestrates the CI/CD pipeline

## Implementation 

### AWS Setup

1. Launched 3 EC2 instances to host Jenkins, SonarQube and Docker server
2. Assigned Elastic IPs to make them publically accessible
3. Opened required ports in Security Groups for access
4. Installed and configured Jenkins, SonarQube and Docker on respective servers

### GitHub Repository

1. Created a GitHub repository to manage source code for the website
2. Added code, tests, configs etc. for the website application
3. Integrated the repo with Jenkins 

### Jenkins Configuration

1. Installed necessary plugins on Jenkins server
2. Created a Jenkins pipeline job
3. Setup webhook in GitHub repo to trigger pipeline on commits
4. Configured stages including Clone Repo, Build Artifact, SonarQube Analysis, Build Docker Image, and Deploy

### SonarQube Integration

1. Installed and configured SonarScanner on Jenkins server
2. Passed SonarQube server credentials and details as environment variables 
3. Added a stage to run SonarQube analysis against source code
4. Published quality gate check results back to Jenkins

### Docker Configuration

1. Created a Dockerfile to package website code
2. Added pipeline stage to build Docker image of the website
3. Pushed image to Docker Hub registry

### Website Deployment 

1. Pull website Docker image in the deployment stage
2. Deploy container with Nginx to render the website
3. Health check added to validate deployment

## Conclusion

The Jenkins pipeline automates continuous analysis, testing and deployment of the website application in a standardized and efficient software delivery process. This results in faster feedback on changes and more reliable updates to production.

Let me know if you need any clarification or have additional questions!
