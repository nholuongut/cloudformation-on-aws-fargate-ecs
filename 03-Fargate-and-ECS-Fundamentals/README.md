# AWS Fargate & ECS Fundamentals

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

## Step-01: Clusters Introduction
-  For introduction slides refer the [Presentation Slides](/12-NhoLuong/Presentations/Cloudformation-on-AWS-ECS-Fargate.pptx). 

## Step-02: Pre-requisite
- Ensure we have a VPC in our region where we are creating the Fargate or ECS clusters.
- **VPC**
    - Name: ecs-vpc
    - IPV4 CIDR Block: 10.0.0.0/16
- **Subnets**
    - Name: ecs-public-1a, CIDR Block: 10.0.10.0/24
    - Name: ecs-public-1b, CIDR Block: 10.0.20.0/24
 - **Internet Gateway**
    - Name: ecs-vpc-igw
 - **Route Tables**
    - Associate public route for main route table.         

## Step-03: ECS Cluster Types & Create a cluster
- We have 3 types of clusters
    - Fargate Cluster (Serverless)
    - ECS EC2 - Linux Cluster
    - ECS EC2 - Windows Cluster

![ECS Cluster Types](/12-NhoLuong/images/01-ECS-Cluster-Types.png)    

### Step-03-01: Create Fargate Cluster
- Cluster Name: fargate-demo
- CloudWatch Container Insights: Enabled
- Verify the newly created cluster

### Step-03-02: Create ECS EC2 Linux Cluster
- **Pre-requisite**: Create a keypair (ecs-mumbai)
- **Clutser Settings**
    - Cluster Name: ecs-ec2-demo
    - Provisioning Model: On-Demand
    - EC2 Instance Type: t2.small
    - Number of Instances: 1
    - EC2 Ami Id: leave defaults
    - EBS storage (GiB): leave defaults
    - Keypair: ecs-mumbai
    - Networking: Select existing VPC and Subnets from ecs-vpc
    - Security group: leave default
    - Container instance IAM role: leave default
    - CloudWatch Container Insights: enabled
- Verify the newly created cluster

## Step-04: Cluster Features

![ECS Cluster Features](/12-NhoLuong/images/03-ECS-Cluster-Features.png) 

## Step-05: Task Definition

### Step-05-01: Task Defintion - Introduction

![ECS TaskDefintion ParameterList](/12-NhoLuong/images/02-ECS-TaskDefintion-ParameterList.png) 

-  For introduction slides refer the [Presentation Slides](/12-NhoLuong/Presentations/Cloudformation-on-AWS-ECS-Fargate.pptx). 

### Step-05-02: Create a simple Task Definition
   - **Task Definition:** nginx-app1-td        
   - **Docker Image:** nholuongut/nginxapp1:latest (Available on Docker Hub)

## Step-06: Create Service
- Create a simple ECS service using the 
- **Configure Service**
    - Launch Type: Fargate
    - Task Definition: nginx-app1
    - Service Name: nginx-app1-svc
    - Number of Tasks: 1
- **Configure Network**
    - VPC: ecs-vpc
    - Subnets: ap-south-1a, ap-south-1b (subnets from both regions)
    - Security Group: ecs-nginx (Inbound Port 80)
    - Auto Assign Public IP: Enabled    
- Access the nginx application
```
http://task-public-ip/app1/index.html
```    
    
## Step-07: Create Task 
- Understand more about a Task
- Create a simple task manually which dont have any association with a service
    - Create Task
    - Stop Task
- Delete a task from Service **nginx-app1-svc** and wait for 5 minutes, task gets automatically recreated. 

## Step-08: Revise ECS Objects
- One more time revise about ECS Objects. 
    - Cluster
    - Service
    - Task Definition
    - Task
- As we go to next steps in our course, these are the words we are going to use very frequently. 

![ECS Objects](/12-NhoLuong/images/04-ECS-Objects.png)


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