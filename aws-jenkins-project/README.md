![](https://github.com/IbrahimmAdel/Banque-Misr-DevOps-Task/blob/master/aws-jenkins-project/Screenshots/Presentation.gif)

---
## Project Structure

The project is structured into multiple phases, each addressing a specific aspect of the infrastructure:

- **Dockerization**: Creating Dockerfiles for the Flask app and PostgreSQL database, along with a Docker Compose file for local testing.
- **Terraform**: Defining infrastructure components such as VPC, subnets, EC2 instance, ECR repository, EKS cluster, and more.
- **Ansible**: Automating the configuration of EC2 instance by installing Jenkins, AWS CLI, kubectl, and Docker.
- **Kubernetes**: Creating Kubernetes manifests for deploying the Flask app and MySQL database on the EKS cluster.
- **Jenkins Pipeline**: Configuring a Jenkins pipeline to automate the build, push, and deployment process.

## Step-by-Step Deployment


### 1. Dockerizing the Application and Database

- Writing Dockerfiles for Flask app and PostgreSQL database.
- Creating a Docker Compose file to run both containers locally for testing.
- For more details: [Docker](https://github.com/IbrahimmAdel/Full-CICD-Project/tree/master/Docker)

### 2. Setting Up the AWS Infrastructure with Terraform

- Creating a VPC with 2 public and 2 private subnets.
- Configuring Internet Gateway (IGW) and Network Address Translation (NAT) Gateways.
- Launching an EC2 instance for hosting Jenkins.
- Creating an Amazon ECR repository for Docker images.
- Provisioning an Amazon EKS cluster with worker nodes in private subnets.
- For more details: [Terraform](https://github.com/IbrahimmAdel/Full-CICD-Project/tree/master/Terraform)

### 3. Configuring EC2 Instance with Ansible

- Installing Jenkins on the EC2 instance using Ansible.
- Setting up AWS CLI, kubectl, and Docker using Ansible playbooks.
- For more details: [Ansible](https://github.com/IbrahimmAdel/Full-CICD-Project/tree/master/Ansible)

### 4. Creating Kubernetes Manifests

- Defining Kubernetes Deployment, Services, StatefulSet, ConfigMap, Secrets, Ingress, PersistentVolume (PV), and PersistentVolumeClaim (PVC) for the Flask app and PostgreSQL database.
- For more details: [Kubernetes](https://github.com/IbrahimmAdel/Full-CICD-Project/tree/master/Kubernetes)

### 5. Jenkins Pipeline Setup

- Installing the **AWS Steps** plugin in Jenkins.
- Configuring GitHub, AWS, and cluster credentials in Jenkins.
- Creating a webhook for GitHub repository to trigger Jenkins pipeline using [ngrok](https://dashboard.ngrok.com/get-started/setup).
- Configuring a Jenkins pipeline to build Docker images, push them to ECR, deploy Kubernetes manifests, and print the application URL.
- For more details: [Jenkins](https://github.com/IbrahimmAdel/Full-CICD-Project/tree/master/Jenkins)

----
## Conclusion

#### This comprehensive DevOps infrastructure deployment project showcases the integration of various tools and technologies to achieve a seamless end-to-end deployment process. By following the step-by-step guide, you have successfully created a robust pipeline for building, deploying, and managing a Flask web application and PostgreSQL database on AWS with Kubernetes. This project provides a strong foundation for scaling and enhancing your DevOps practices.





