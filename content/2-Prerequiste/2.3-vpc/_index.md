---
title : "Create VPC "
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---


#### Create VPC, subnets, route tables, internet gateway
1. Access the [VPC management interface](https://console.aws.amazon.com/vpc/home)
  + Click **Your VPCs**.
  + Click **Create VPC**.

![VPC](/images/2.prerequisite/001-createvpc.png)

2. At the **Create VPC** page.
  + **Name tag**, enter **Demo VPC**.
  + **IPv4 CIDR**, enter **10.10.0.0/16**.
  + **Number of Availability Zones (AZs)** select **2**.
  + **Number of public subnets** select **2**.
  + **Number of private subnets** select **0**.
  + **VPC endpoints**, select **None**.
  + Click **Create VPC** at the bottom of the page.

![VPC](/images/2.prerequisite/002-createvpc.png)

3. View the details of the newly created VPC.
![VPC](/images/2.prerequisite/003-detailvpc.png)

4. Allocate a public IP address for Public subnet 1.
  + Open **Subnet** menu.
  + Select **PublicSubnet1**.
  + Select **Edit subnet settings**.
  ![VPC](/images/2.prerequisite/004-enablepublicIPforsubnet.png)

  + Check the **Enable auto-assign public IPv4 address** box
    ![VPC](/images/2.prerequisite/005-enablepublicIP.png)
  + Cick button **Save**

5. Verify that the allocation was successful.
![VPC](/images/2.prerequisite/006-enablesuccess.png)

6. Then do the same with Public subnet 2