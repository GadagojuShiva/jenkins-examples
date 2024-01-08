# Spring Boot Application Deployment with ArgoCD, Jenkins, SonarQube, Maven, and Kubernetes

This project demonstrates the deployment of a Spring Boot application in Kubernetes using ArgoCD for continuous delivery, Jenkins for CI/CD, SonarQube for code quality analysis, Maven for build management, and Kubernetes for container orchestration.

## Project Overview

This project showcases the deployment of a Spring Boot application in a Kubernetes cluster using industry-standard tools for continuous integration, continuous deployment, and code quality monitoring.
## Architecture

![Alt Text](https://github.com/GadagojuShiva/jenkins-examples/blob/main/Architecture.jpg)

## Prerequisites

Before getting started, ensure you have the following prerequisites installed and configured:

- Java Development Kit (JDK)
- Maven
- Docker
- Kubernetes cluster
- Jenkins
- ArgoCD
- SonarQube

# Jenkins Installation and Docker Configuration

## Install Java (JDK)

```bash
sudo apt update
sudo apt install openjdk-11-jre
java -version
```


## Install Jenkins

```bash
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```
- Open Port 8080 for Jenkins in AWS Security Group
- Navigate to EC2 > Instances > Select your instance
- In the bottom tabs, click on "Security"
- Add inbound traffic rule: Type: All traffic, Protocol: All, Port Range: 8080

## Access Jenkins

- Visit http://<ec2-instance-public-ip>:8080 in your web browser
- Retrieve Jenkins Admin Password:

    ```bash
    sudo cat /var/lib/jenkins/secrets/initialAdminPassword
    ```
- Enter the Administrator password

## Jenkins Initial Setup
- Click on "Install suggested plugins" and wait for installation to complete
- Create First Admin User or skip the step
- Docker Pipeline Plugin Installation
- Log in to Jenkin
- Go to Manage Jenkins > Manage Plugins
- In the Available tab, search for "Docker Pipeline"
- Select the plugin and click Install
- Restart Jenkins after the plugin is installed
## Docker Installation and Configuration

```bash
    sudo apt update
    sudo apt install docker.io
    sudo su -
    usermod -aG docker jenkins
    usermod -aG docker ubuntu
    systemctl restart docker

```
## Restart Jenkins
```bash
    http://<ec2-instance-public-ip>:8080/restart
```
**After completing these steps, your Jenkins instance will be set up with Docker support, and you can start using Jenkins for your CI/CD pipelines.**