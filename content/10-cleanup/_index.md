---
title : "Clean up resources "
date : 2023
weight : 10
chapter : false
pre : "<b> 10. </b>"
---

We will take the following steps to delete the resources we created in this exercise.

### Delete EB enviroment:

- Access  **Elastic Beanstalk Management Console**
- Open menu **Enviroment**, tick the enviroment created in the lab, click the **Action** button and then select **Terminate enviroment**.

### Delete Security group

1. Access **EC2**
2. Click **Security Group**
3. Select security groups related to the lab.
4. Click **Actions**
5. Click **Delete security group**

### Delete Keypair

1. Access **EC2**
2. Click **Key Pairs**
3. Click **Actions**
4. Click **Delete**

#### Delete User pool

1. Access Cognito
2. Select User pool
3. Click **Delete**

#### Delete VPC

1. Access **VPC**
2. Select **Your VPCs**
3. Select the VPCs related to the lab
4. Click **Actions**
5. Click **Delete VPC**


#### Delete Certificates 

1. Access **ACM**
2. Click **List certificates**
3. Select the VPCs related to the lab
4. Click **Delete**

#### Delete Hosted zone 

1. Access **Route 53** 
2. Select **Hosted zone**
3. Select the Hosted zone related to the lab
4. Click **Delete**