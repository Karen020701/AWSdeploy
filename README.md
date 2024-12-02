# AWSDeploy

This project is a web application using HTML that makes use of a Docker container. 
The goal of this practice is continuous integration and continuous deployment (CI/CD) on an AWS instance.

## Prerequisites

In order to execute the project you must take into account the configuration of:
- Docker Hub
To have an account in Docker Hub to be able to generate an image.
Generate the desired image.
- Instances in AWS
An EC2 instance must be generated in AWS.
The instance created must be configured with SSH keys to allow communication.
Within the security of the EC2 instance must be configured for the HTTP port 80 that will allow the connection with the container.

In this case to generate a connection you must make use of a GitHub secret keys and have access to the containers

  - DOCKER_USERNAME: Docker Hub username.
  - DOCKER_PASSWORD: Can be a Docker Hub password or an access token.
  - EC2_SSH_KEY: Private SSH key that will allow access to the EC2 instance.
  - EC2_PUBLIC_IP: Public IP address of the EC2 instance.

## Connection configuration
1. Generate secret keys on GitHub
Inside your GitHub repository on the right hand side select Settings > Secrets and variables > Actions.
The following is added:
  - DOCKER_USERNAME: User Name
  - DOCKER_PASSWORD: Docker Hub Password or Token
  - EC2_SSH_KEY: Private SSH key that will allow access to the EC2 instance.
  - EC2_PUBLIC_IP: Public IP address of your EC2 instance.
2. Create a Dockerfile
Dockerfile is a text file containing a set of instructions that Docker uses to build a custom container image. 
3. Create a pipeline.yml
A pipeline.yml file in a project is a configuration script that defines the automated steps needed to deploy, test and deploy your application. 
When using an AWS CI/CD service, this file details the instructions the system must follow to manage the deployment in AWS. 
deployment on AWS.
Here you place the connection keys generated in GitHub to allow the automation of the Git Actions for the project ensuring that the changes are verified within the deployment.

## Check if the connection is correct:
Some changes must be made to the project code.
Once the connection is established Git Actions should generate an automatic workflow.
Once this is done, it is observed that the deploy is automatically generated in the instance showing the updated image of the change in the project.
