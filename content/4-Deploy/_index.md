---
title : "Deploy application"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b>4</b> "
---
#### Prepare application
+ Please download the following zip file, extract it, and then add the following information to the .env file.

  [Link download](https://drive.google.com/file/d/1XK2ioRU1eM5eZSxw5rKr0Sh-v2u9oi9M/view?usp=sharing)
```
COGNITO_CLIENT_ID=your client ID
COGNITO_CLIENT_SECRET=your client secrect 
COGNITO_LOGOUT_URL=cognitodomain/logout
COGNITO_LOGOUT_REDIRECT_URI=sign-out URLs
```
![EB](/images/2.prerequisite/eb/1.png)

+ Zip file again.

#### Deploy application
1.  Access to [Amazon Elastic Beanstalk management console](https://console.aws.amazon.com/elasticbeanstalk/home).
  + Click **Create application**.
  ![EB](/images/2.prerequisite/eb/001.png)
    
2. At the  **Configure environment** screen
  + In the **Environment tier** section, select **Web server environment**.
  + In the **Application name** field, enter **demo**.
  + In the **Domain** field, enter the domain you want and then click **Check availability** to see if you can use that domain.
  ![EB](/images/2.prerequisite/eb/002.png)

  + In the **Platform type** section, select **Managed platform**.
  + In the **Application code** section, select **Upload your code**.
  + In the **Version label** field, enter **v1**.
  + Click **Choose file** and then upload the compressed file earlier.
  ![EB](/images/2.prerequisite/eb/003.png)

  + In the **Configuration presets** field, select **High availability**.
  + Click **Next**.
  ![EB](/images/2.prerequisite/eb/003-1.png)

3. At the **Configure service access** screen
  + In the **Service role** section, select **aws-elasticbeanstalk-service-role**.
  + In the **EC2 key pair** section, select the key pair you want.
  + In the **EC2 instance profile** section, select **Redis_role**.
  + Click **Next**
  ![EB](/images/2.prerequisite/eb/004.png)

4. At the **Set up networking, database, and tags** screen
  + In the **VPC** section, select **Demo-vpc**.
  + In the **Public IP address** section, tick the **Activated** checkbox.
  + In the **Instance subnets** section, select the 2 created public subnets.
  + Scroll to the bottom of the page, click **Next**
  ![EB](/images/2.prerequisite/eb/005.png)

5. At the **Configure instance traffic and scaling** screen
  + In the section **Root volume type**, select **General Purpose(SSD)**.
  + In the **Size** field, enter **10**.
  ![EB](/images/2.prerequisite/eb/006.png)

  + In the **EC2 security groups** section, select **SG Public Linux Instance**.
  + In the **Auto scaling group** section, enter min instances as **2**, max as **3**.
  ![EB](/images/2.prerequisite/eb/007.png)
 + Scroll down to **Instance types** field, select **t2.micro**.
  ![EB](/images/2.prerequisite/eb/008.png)

  + In the **Load balancer subnets** section, select the 2 created public subnets.
  ![EB](/images/2.prerequisite/eb/009.png)

  + Under **Load Balancer Type**, select **Application load balancer**.
  + Select **Dedicated** to create a new ALB.
  + In the **Listener** section, click **Add listener** to open the **Add listener** popup.
  ![EB](/images/2.prerequisite/eb/010.png)

  + At **Listener port**, enter **443**.
  + In the **Listener protocol** field, enter **HTTPS**.
  + In the **SSL certificate** section, select the generated certificate.
  + In the **SSL policy** section, select **ELBSecurityPolicy-TLS13-1-2-2021-06**.
  + Click **Save**
  ![EB](/images/2.prerequisite/eb/011.png)

  + Scroll down to the bottom, click **Next**.

  6/ At the **Configure updates, monitoring, and logging** screen
  + Scroll down to **Container options** section.
  + In the **Proxy server** section, select **Apache**.
  + In the **Document root** field, enter **/cognito-redis/public**.
  + Scroll down to the bottm, click **Next**.
  ![EB](/images/2.prerequisite/eb/012.png)

  7/ At the **Review** screen
  + Scroll down to the bottm, click **Submit**.

---
#### Chuẩn bị ứng dụng
+ Bạn hãy tải file zip sau về, giải nén ra, rồi bổ sung các thông tin sau vào file .env.

  [Link download](https://drive.google.com/file/d/1XK2ioRU1eM5eZSxw5rKr0Sh-v2u9oi9M/view?usp=sharing)
```
COGNITO_CLIENT_ID=your client ID
COGNITO_CLIENT_SECRET=your client secrect 
COGNITO_LOGOUT_URL=cognitodomain/logout
COGNITO_LOGOUT_REDIRECT_URI=sign-out URLs
```
![EB](/images/2.prerequisite/eb/1.png)

+ Zip file lại.

#### Triển khai ứng dụng
1.  Truy cập vào [giao diện quản trị của dịch vụ Amazon Elastic Beanstalk](https://console.aws.amazon.com/elasticbeanstalk/home).
  + Click **Create application**.
  ![EB](/images/2.prerequisite/eb/001.png)
    
2. Tại màn hình **Configure environment**
  + Tại mục **Environment tier**, chọn **Web server environment**.
  + Tại mục **Application name**, nhập **demo**.
  + Tại mục **Domain**, nhập domain bạn muốn rồi ấn **Check availability** để xem có thể dùng domain đó không.
  ![EB](/images/2.prerequisite/eb/002.png)

  + Tại mục **Platform type**, chọn **Managed platform**.
  + Tại mục **Application code**, chọn **Upload your code**.
  + Tại mục **Version label**, nhập **v1**.
  + Click **Choose file** rồi upload file đã nén ban nãy.
  ![EB](/images/2.prerequisite/eb/003.png)

  + Tại mục **Configuration presets**, chọn **High availability**.
  + Click **Next**.
  ![EB](/images/2.prerequisite/eb/003-1.png)

3. Tại màn hình **Configure service access**
  + Tại mục **Service role**, chọn **aws-elasticbeanstalk-service-role**.
  + Tại mục **EC2 key pair**, chọn key pair bạn muốn.
  + Tại mục **EC2 instance profile**, chọn **Redis_role**.
  + Click **Next**
  ![EB](/images/2.prerequisite/eb/004.png)

4. Tại màn hình **Set up networking, database, and tags**
  + Tại mục **VPC**, chọn **Demo-vpc**.
  + Tại mục **Public IP address**, tick vào checkbox **Activated**.
  + Tại mục **Instance subnets**, chọn 2 public subnet đã tạo.
  + Scroll xuống cuối trang, click **Next**
  ![EB](/images/2.prerequisite/eb/005.png)

5. Tại màn hình **Configure instance traffic and scaling**
  + Tại mục **Root volume type**, chọn **General Purpose(SSD)**.
  + Tại mục **Size**, nhập **10**.
  ![EB](/images/2.prerequisite/eb/006.png)

  + Tại mục **EC2 security groups**, chọn **SG Public Linux Instance**.
  + Tại mục **Auto scaling group**, nhập min instances là **2**, max là **3**.
  ![EB](/images/2.prerequisite/eb/007.png)
  + Scroll xuống dưới, đến mục **Instance types**, chọn **t2.micro**.
  ![EB](/images/2.prerequisite/eb/008.png)

  + Tại mục **Load balancer subnets**, chọn 2 public subnet đã tạo.
  ![EB](/images/2.prerequisite/eb/009.png)

  + Tại mục **Load Balancer Type**, chọn **Application load balancer**.
  + Chọn **Dedicated** để tạo mới ALB.
  + Tại mục **Listener**, click **Add listener** để mở popup **Add listener**.
  ![EB](/images/2.prerequisite/eb/010.png)

  + Tại mục **Listener port**, nhập **443**.
  + Tại mục **Listener protocol**, nhập **HTTPS**.
  + Tại mục **SSL certificate**, chọn certificate đã tạo.
  + Tại mục **SSL policy**, chọn **ELBSecurityPolicy-TLS13-1-2-2021-06**.
  + Click **Save**
  ![EB](/images/2.prerequisite/eb/011.png)

  + Scroll xuống cuối trang, click **Next**.

  6/ Tại màn hình **Configure updates, monitoring, and logging**
  + Scroll xuống đến mục **Container options**.
  + Tại mục **Proxy server**, chọn **Apache**.
  + Tại mục **Document root**, nhập **/cognito-redis/public**.
  + Scroll xuống cuối trang, click **Next**.
  ![EB](/images/2.prerequisite/eb/012.png)

  7/ Tại màn hình **Review**
  + Scroll xuống cuối trang, click **Submit**.

 
