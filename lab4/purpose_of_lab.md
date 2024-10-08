# Purpose of lab/Lab4
Design Rehosting Migration V2 in your Cloud Migration course is to develop a high-level design (HLD) document for a lift-and-shift migration of an application consisting of two virtual machines: WebServerVM and SQLVM


## Components

1. **WebServerVM**:
   - **Node.JS**: This represents the existing virtual machine (VM) hosting a Node.js application.

2. **SQLVM**:
   - **SQL Server Database**: This represents the existing VM hosting a SQL Server database.

3. **Docker Image**:
   - The Node.js application from WebServerVM is containerized into a Docker image.

4. **Azure Container Registry (ACR)**:
   - The Docker image is pushed to ACR, a managed Docker registry service in Azure.

5. **Azure Kubernetes Service (AKS)**:
   - **Node.js Application**: The containerized Node.js application is deployed to AKS.
   - **Kubernetes Pods**: The application runs within Kubernetes pods, which are the smallest deployable units in Kubernetes.
   - **Traffic Distribution**: AKS uses a load balancer to distribute incoming traffic across multiple instances of the application for high availability and scalability.

6. **Azure Managed SQL Database**:
   - The SQL Server database from SQLVM is backed up and migrated to Azure SQL Database, a fully managed relational database service.

## Interactions

1. **Containerization**:
   - The Node.js application on WebServerVM is containerized into a Docker image.

2. **Pushing to ACR**:
   - The Docker image is pushed to Azure Container Registry for storage and management.

3. **Deployment to AKS**:
   - The Docker image is deployed from ACR to the AKS cluster.

4. **Running in Kubernetes Pods**:
   - The Node.js application runs within Kubernetes pods in the AKS cluster.

5. **Traffic Distribution**:
   - A load balancer in AKS distributes incoming traffic across multiple pods to ensure high availability and scalability.

6. **Database Migration**:
   - The SQL Server database on SQLVM is backed up and migrated to Azure Managed SQL Database.

#### Summary

The diagram shows the process of migrating an existing application to Azure by containerizing the web server and deploying it to Azure Kubernetes Service (AKS) for scalability and high availability. The SQL Server database is migrated to Azure Managed SQL Database for managed services and reliability. This setup ensures minimal downtime and leverages Azure's cloud capabilities for better performance and management.