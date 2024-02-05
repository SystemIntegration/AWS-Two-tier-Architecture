# Two-Tier Architecture CloudFormation Template

This CloudFormation template automates the deployment of a two-tier architecture on Amazon Web Services (AWS). The architecture consists of a web application front-end tier and a database back-end tier. This README file provides instructions on using the CloudFormation template to set up the architecture without auto-scaling.

## Prerequisites

- **AWS Account:** You need an active AWS account to deploy resources using CloudFormation.
- **AWS CLI:** Install and configure the AWS Command Line Interface (CLI) with appropriate credentials.
- **Basic Knowledge:** Familiarity with AWS services, CloudFormation, and networking concepts will be helpful.

## Architecture Overview

The architecture created by this CloudFormation template consists of the following components:

**Web Tier:**

- Amazon EC2 Instances
- Elastic Load Balancer (ELB)
- Security Group for Web Instances
- IAM Roles and Policies for EC2 Instances

**Database Tier:**

- Amazon RDS Instance (Relational Database Service)
- Security Group for Database

## Usage

1. **Clone Repository:** Clone this repository to your local machine or download the template file.
2. **Customize Parameters:** Open the `twotier.yml` CloudFormation template in a text editor. Customize parameters such as instance types, database settings, etc.
3. **Deploy Stack:**

   - Using AWS Management Console:
     ```bash
     aws cloudformation create-stack --stack-name YourStackName --template-body file://twotier.yml --parameters ParameterKey=ParameterName,ParameterValue=ParameterValue
     ```

4. **Monitor Stack Creation:** After initiating the stack creation, monitor the progress in the AWS Management Console or CLI. Once the stack reaches the "CREATE_COMPLETE" status, the architecture is deployed.
5. **Access Web Application:** Use the Elastic Load Balancer DNS name to access the web application.

## Clean Up

Remember to clean up resources when they are no longer needed to avoid unnecessary charges.

- **Delete Stack:**
  - Using AWS Management Console:
    ```bash
    aws cloudformation delete-stack --stack-name YourStackName
    ```

- **Verify Deletion:** Ensure that all resources associated with the stack are successfully deleted. Check the AWS Management Console or CLI.

## Security Considerations

- **Security Groups:** Review and customize security group settings to restrict traffic appropriately between tiers.
- **IAM Roles:** Follow the principle of least privilege while defining IAM roles and policies for instances.
- **Encryption:** Implement encryption for sensitive data, both at rest and in transit.
- **Access Control:** Regularly review and update access control settings for resources.

## Disclaimer

This CloudFormation template is provided as-is. While efforts have been made to ensure its accuracy, it's recommended to review and test the template in your own environment before deploying in production.

## Resources

- [AWS CloudFormation Documentation](https://docs.aws.amazon.com/cloudformation/)
- [AWS Architecture Center](https://aws.amazon.com/architecture/)
- For any issues or questions, please feel free to open an issue in this repository.
