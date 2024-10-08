# Cloud Infrastructure as Code (IaC) Project

## Project Overview

This repository contains the implementation of Cloud Infrastructure as Code (IaC) as part of the assessment task for ICTCLD505: Implement Cloud Infrastructure with Code. The project involves deploying and managing a microservices-based LAMP stack using AWS CloudFormation. The project demonstrates best practices in cloud infrastructure automation, parameterization, and template-driven deployments in AWS.

## Project Structure

The project follows a structured workflow divided into the following key parts:

1. **Part 1: Prepare to Deploy and Configure** 
   - Evaluating and selecting the appropriate cloud platform (AWS)
   - Comparative analysis of IaC technologies (CloudFormation, Terraform, Ansible)
   - Identification of benefits of IaC, such as scalability, disaster recovery, and compliance
   - Selection of automation techniques leveraging cloud platforms

2. **Part 2: Cloud Infrastructure as Code Pre-defined Template**
   - Use of AWS CloudFormation to deploy predefined infrastructure (LAMP stack)
   - Deployment of resources such as VPCs, EC2, RDS, security groups
   - Command-line interface (CLI) and console orchestration of deployments
   - Testing and troubleshooting of templates

3. **Part 3: Develop and Update IaC Templates**
   - Custom templates for deploying multi-tier applications on AWS
   - Use of parameters for dynamic configuration
   - Template updates for modifying, adding, or removing resources
   - Implementation of secrets using AWS CLI and ensuring containerized applications access the secrets securely

4. **Part 4: Contingency Tasks and Cloud Knowledge Concepts**
   - Risk management and contingency planning for cloud infrastructure failure
   - Compliance with international standards (ISO/IEC 17789, ISO/IEC 19086-1)
   - Best practices for managing IaC, including version control, idempotency, and testing frameworks

## CloudFormation Template

This project utilizes AWS CloudFormation to define, provision, and manage the following cloud infrastructure resources:

- **VPC (Virtual Private Cloud)**: A secure, isolated virtual network with public and private subnets.
- **EC2 Instance**: Hosting the LAMP stack web application.
- **RDS Instance**: A managed MySQL database configured with multi-AZ deployment.
- **Security Groups**: Controlling access to both the web server and database resources.
- **S3 Bucket**: Storing additional application resources and backups.

## How to Deploy

To deploy the infrastructure, follow these steps:

1. **Clone the repository**:
    ```bash
    git clone https://github.com/your-repo-name.git
    ```

2. **Prepare the AWS CLI**:
    Ensure that the AWS CLI is configured with appropriate access keys and permissions to deploy resources.

3. **Deploy the CloudFormation Stack**:
    From the AWS Management Console:
    - Navigate to CloudFormation.
    - Select **Create Stack** and upload the CloudFormation template provided in the `/templates` directory.
    - Monitor the stack creation and ensure the status is **CREATE_COMPLETE**.

4. **Access the EC2 Instance**:
    Once the stack is deployed:
    - Retrieve the public IP address from the EC2 dashboard.
    - SSH into the EC2 instance:
      ```bash
      ssh -i "your-key.pem" ec2-user@your-ec2-public-ip
      ```

5. **Verify Application Deployment**:
    - Access the web application via the public DNS of the EC2 instance.
    - Verify the MySQL database connection using the credentials specified in the RDS template.

6. **Update Resources**:
    - To update any resource, modify the CloudFormation YAML template and redeploy via the AWS Console or CLI.

7. **Cleanup**:
    To avoid incurring charges, delete the CloudFormation stack once testing is complete:
    ```bash
    aws cloudformation delete-stack --stack-name YourStackName
    ```

## Testing and Troubleshooting

During the deployment process, various template errors were encountered and resolved. All identified errors and their solutions are documented in the troubleshooting logs found in the `/logs` directory. Example issues include incorrect parameterization and improper security group configurations. Detailed solutions for each error can be found in the **/logs/troubleshooting.md** file.

## Conclusion

This project demonstrates the use of CloudFormation to automate the deployment and management of cloud infrastructure for a microservices-based LAMP stack. Key features include modular templates, version-controlled deployments, and best practices in managing cloud resources using IaC.

For further details, refer to the full project documentation available in the `/docs` directory.

## Contact

For any issues or inquiries regarding this project, please contact [Your Name] at [Your Email].
