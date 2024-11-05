# Cloud Formation Templates for Deploying Fargate Tasks in a VPC on a Public Subnet.

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

## What are we going to build using CloudFormation Templates?

![ECS CFN Public VPC Public Subnet](/12-NhoLuong/images/11-ecs-cfn-public-vpc-public-subnet.png)

## Step-00: Template Categories
- We are going to divide templates in to two categories
- **Network Stack (Parent Stack)**
    - Create VPC
    - Create ECS Cluster & ECS Roles
    - Create Load Balancer (ALB)
    - Create Outputs
- **Faragte Service Stack**
    - Create Input Parameters
    - Create Task Definition
    - Create Load Balancer Target Group & Load Balancer Rule
    - Create ECS Service

## Step-01: Create Network Stack (Parent Stack)
- We are going to build the network stack in a incremental manner.     
    - 01-01-Fargate-NetworkStack-CreateVPC.yml
    - 01-02-Fargate-NetworkStack-Create-ECSCluster-ECSRoles.yml
    - 01-03-Fargate-NetworkStack-Create-SecurityGroups-LoadBalancers.yml
    - 01-04-Fargate-NetworkStack-Create-Outputs.yml

## Step-02: Create Fargate Service Stack
- We are going to build the network stack in a incremental manner.     
    - 02-01-Fargate-ServiceStack-Create-InputParameters.yml
    - 02-02-Fargate-ServiceStack-Create-TaskDefinition.yml
    - 02-03-Fargate-ServiceStack-Create-ALB-TargetGroup-and-LoadBalancerRule.yml
    - 02-04-Fargate-ServiceStack-Create-ECSService.yml

## Step-03: Clean-Up
- Delete CloudFormation Stacks 
    - First delete Service Stack
    - Next delete the Network Stack ( Network stack resources are used in Service Stack - Always recommended to delete parent stacks at the end.)
    
![](https://i.imgur.com/waxVImv.png)
# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact Me]
* [Name: Nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)
* [PayPal.me](https://www.paypal.com/paypalme/nholuongut)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟