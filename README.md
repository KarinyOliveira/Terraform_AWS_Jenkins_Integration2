# Terraform_AWS_Jenkins_Integration2

The project demonstrates the use of **Terraform** for automating the provisioning and management of cloud infrastructure. It aims to showcase the practical application of **Infrastructure as Code (IaC)** principles for setting up and deploying cloud resources, especially for CI/CD workflows, using tools like **Terraform** and cloud services such as **AWS**.

## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Setup and Installation](#setup-and-installation)
- [Terraform Commands](#terraform-commands)
- [Usage](#usage)
- [Technologies Used](#technologies-used)

## Project Overview

The **FinalExam1Devops2Terraform** project leverages **Terraform** to automate the creation and management of cloud infrastructure, specifically on **AWS** (Amazon Web Services). The infrastructure includes the provisioning of resources necessary for building a CI/CD pipeline, such as EC2 instances, security groups, IAM roles, and S3 buckets for storing build artifacts.

The main goal of the project is to demonstrate the power of **Infrastructure as Code (IaC)** by using Terraform to deploy and manage cloud resources without manual intervention.

## Features

- **Automated Infrastructure Provisioning**: Use Terraform to provision AWS resources such as EC2 instances, security groups, S3 buckets, IAM roles, and more.
- **Reusable Modules**: Terraform modules to modularize the infrastructure setup.
- **Scalable Infrastructure**: Easily modify or scale the resources in AWS to meet project requirements.
- **Version Control with Git**: All infrastructure configurations are managed through Git, ensuring version control and collaboration.
- **Secure AWS Resources**: Proper configuration of IAM roles and policies for securing cloud resources.

## Prerequisites

Before getting started, ensure you have the following tools installed on your local machine:

- **Git**: For cloning the repository and version control.
- **Terraform**: Infrastructure-as-Code (IaC) tool used to provision the resources.
  - Install Terraform from [here](https://www.terraform.io/downloads).
- **AWS CLI**: Command-line tool to interact with AWS.
  - Install AWS CLI from [here](https://aws.amazon.com/cli/).
  - Configure AWS CLI with `aws configure` using your AWS Access Key, Secret Key, and Region.
- **AWS Account**: You need an active AWS account with necessary permissions to provision EC2 instances, IAM roles, and other resources.

## Setup and Installation

Follow these steps to set up and provision the infrastructure using Terraform:

### 1. Clone the Repository

Clone the repository to your local machine:

```bash
git clone https://github.com/KarinyCCTB/FinalExam1Devops2Terraform.git
cd FinalExam1Devops2Terraform
```

### 2. Configure AWS CLI

Make sure AWS CLI is configured with your credentials:

```bash
aws configure
```

Enter your AWS `Access Key ID`, `Secret Access Key`, `Default Region Name`, and `Default Output Format` when prompted.

### 3. Initialize Terraform

Run the following command to initialize the Terraform working directory. This will download the required providers and modules:

```bash
terraform init
```

### 4. Review the Terraform Plan

Before applying any changes, review what Terraform will do by running:

```bash
terraform plan
```

This will show you a preview of the resources that Terraform will create or modify on AWS.

### 5. Apply the Terraform Configuration

Once you're happy with the Terraform plan, apply the configuration to create the resources:

```bash
terraform apply
```

Terraform will ask for confirmation. Type `yes` and press **Enter** to proceed. Terraform will then provision the AWS resources according to the configuration.

### 6. Access Your Infrastructure

After the infrastructure is successfully provisioned, Terraform will output information such as the **public IP address** of any created EC2 instances or URLs to other services (e.g., S3). Use these outputs to interact with the deployed resources.

## Terraform Commands

Here are some key Terraform commands that you will find useful:

- **Initialize Terraform working directory** (downloads the required providers):

    ```bash
    terraform init
    ```

- **Show the execution plan** (before applying changes):

    ```bash
    terraform plan
    ```

- **Apply the configuration to create or update resources**:

    ```bash
    terraform apply
    ```

- **Destroy the infrastructure** (to clean up the resources after use):

    ```bash
    terraform destroy
    ```

- **Validate the Terraform configuration** (check for syntax errors and other issues):

    ```bash
    terraform validate
    ```

## Usage

Once the infrastructure is provisioned:

1. **Access EC2 Instance**: Use the public IP address of the EC2 instance to SSH into it.
2. **Set Up Your CI/CD Pipeline**: You can configure Jenkins or any other CI/CD tools on the EC2 instance to start automating deployments.
3. **Store Build Artifacts in S3**: Use the provisioned S3 bucket to store Jenkins build artifacts, logs, or any other necessary files.

### Example: Connect to EC2 Instance

To connect to your EC2 instance:

```bash
ssh -i <your-ec2-keypair.pem> ec2-user@<ec2-public-ip>
```

Replace `<your-ec2-keypair.pem>` with your private key file and `<ec2-public-ip>` with the public IP address provided by Terraform.

## Technologies Used

- **Terraform**: Infrastructure-as-Code tool to manage and provision cloud resources.
- **AWS EC2**: Virtual machine instances for hosting applications.
- **AWS S3**: Object storage used for storing build artifacts and other assets.
- **AWS IAM**: Securely manage permissions for resources in AWS.
- **AWS Security Groups**: Used for managing access control and firewall rules.
- **AWS CLI**: Command-line tool for interacting with AWS services.
- **Git**: Version control for managing and collaborating on code.
