# Jenkins Pipeline 

> This document provides an overview of the Jenkins pipeline for building and deploying Dockerized applications to AWS EKS.

## Requirements
- install [AWS Steps plugin](https://plugins.jenkins.io/pipeline-aws/#plugin-content-withaws)


## Pipeline Overview

The Jenkins pipeline follows these stages to build, push, and deploy Docker images to AWS ECR and an EKS cluster:

1. **Build Images:** Build and tag Docker images for the Flask App and PostgreSQL DB.

2. **Push Images:** Push Docker images to AWS ECR after logging in using AWS credentials.

3. **Remove Images:** Remove local Docker images from the Jenkins server.

4. **Deploy k8s Manifests:** Update Kubernetes deployment and statefulset manifests with new ECR image versions and deploy them to an EKS cluster.

5. **Website URL:** Retrieve the URL of the deployed website and display it in the console.

## Environment Variables

The following environment variables are used in the Jenkins pipeline:

- `ECR_REPO`: ECR repository URI.
- `APP_IMAGE_NAME`: Name of the Flask App image.
- `DB_IMAGE_NAME`: Name of the PostgreSQL DB image.
- `APP_PATH`: Path to the App Dockerfile in the GitHub repo.
- `DB_PATH`: Path to the DB Dockerfile in the GitHub repo.
- `DEPLOTMENT_PATH`: Path to the deployment.yml in the GitHub repo.
- `STATEFULSET_PATH`: Path to the statefulset.yml in the GitHub repo.
- `AWS_CREDENTIALS_ID`: AWS credentials variable ID in jenkins-credentials.
- `KUBECONFIG_ID`: EKS-cluster credentials variable ID in jenkins-credentials.

