2048 Game Deployment with AWS EKS
This README provides a comprehensive guide for deploying the 2048 game application using Amazon Web Services (AWS) Elastic Kubernetes Service (EKS) and Virtual Private Cloud (VPC).

Prerequisites
Ensure you have the necessary tools installed and configured, including AWS CLI, kubectl, eksctl, and Helm. These tools will allow you to manage your AWS resources, interact with your Kubernetes cluster, and deploy the necessary applications.

Steps
1. Create EKS Cluster
Begin by setting up an EKS cluster with Fargate support. This step involves creating a managed Kubernetes cluster in AWS that utilizes Fargate, allowing you to run containers without managing the underlying EC2 instances.

2. Create Fargate Profile
Next, configure a Fargate profile specifically for the game-2048 namespace. This ensures that all the pods within this namespace will run on Fargate, simplifying resource management and scaling.

3. Deploy the 2048 Application
Deploy the 2048 game application by applying the deployment files located in the project folder. These files will create the necessary Kubernetes resources, including the namespace, deployment, service, and ingress, to run the 2048 game on the EKS cluster.

4. Associate IAM OIDC Provider
Set up an IAM OIDC provider for your EKS cluster. This step is crucial for creating the IAM roles and policies needed to enable the AWS Load Balancer Controller, which will manage your application's ingress resources.

5. Install ALB Ingress Controller
Install the AWS Application Load Balancer (ALB) Ingress Controller using Helm. The ALB Ingress Controller integrates with your EKS cluster and manages the ALB for routing external traffic to your Kubernetes services.

6. Verify Deployment
After deploying the application and ingress controller, verify that everything is running smoothly. Check the status of your pods and services to ensure the 2048 game application is up and accessible.

7. Access the Application
Finally, retrieve the external endpoint for the 2048 game application by inspecting the ingress resource. Use this endpoint to access the game through your web browser.
