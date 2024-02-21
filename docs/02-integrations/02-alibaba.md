
# Alibaba Integration (3 minutes)

If you want to know why not use AWS, please read the [Why should you not use AWS Lambda as the Function for Serverless WordPress?](https://www.serverless-wordpress.cloud/2024/01/08/why-not-aws-lambda/) blog.

In this guide, we will show you below questions:

1. How to create a RAM Role to allow Lougao to access your Alibaba Cloud resources?
2. How to obtain the **ARN** for that role?
3. How to obtain the Alibaba Cloud **Main Account ID**?

After you have the above information, you can use it to integrate Lougao with your Alibaba Cloud account.

:::tip Before you start

Before you start, you need to have an Alibaba Cloud account. If you don't have an Alibaba Cloud account, you can create one [here](https://account.alibabacloud.com/register/intl_register.htm). 

:::

## Create a RAM Role

1. Go to the Alibaba Cloud Console: [https://home-intl.console.aliyun.com/](https://home-intl.console.aliyun.com/)
2. Search for RAM, click on **Resource Access Management**: ![Alibaba Cloud Resource Access Management](https://r2.serverless-wordpress.cloud/2024/02/screenshot-20240206-194316-2048x1374.png)
3. Create a Role: ![Create a Role](https://r2.serverless-wordpress.cloud/2024/02/screenshot-20240206-194601-2048x1374.png)
4. Select **Alibaba Cloud Account**.
5. Enter RAM Role Name: ![Enter RAN Role Name](https://r2.serverless-wordpress.cloud/2024/02/screenshot-20240206-194841-2048x1374.png)
6. Click the **Add Permissions to RAM Role** button. ![Add Permissions to RAM Role](https://r2.serverless-wordpress.cloud/2024/02/screenshot-20240206-195047-2048x1374.png)
7. Click the **Grant Permission** button and add permissions to the RAM Role: ![Grant Permission](https://r2.serverless-wordpress.cloud/2024/02/screenshot-20240206-200032-2048x1374.png)
8. Edit **trust policy**, copy and paste the following code:

```json
{
  "Statement": [
    {
      "Action": "sts:AssumeRole",
      "Effect": "Allow",
      "Principal": {
        "RAM": [
          "acs:ram::1193858969452899:user/lougao-console"
        ]
      }
    }
  ],
  "Version": "1"
}
```

![Edit trust policy](https://r2.serverless-wordpress.cloud/2024/02/screenshot-20240206-200255-2048x1374.png)

Congratulations! You have created a RAM Role to allow Lougao to access your Alibaba Cloud resources, after you have the **ARN** for that role and the Alibaba Cloud **Main Account ID**, you can use it to integrate Lougao with your Alibaba Cloud account.

## Obtain the ARN for the Role

You can obtain the **ARN** for the role you created at the **Basic Information** page of the role.

![Obtain the ARN for the Role](https://r2.serverless-wordpress.cloud/2024/02/screenshot-20240206-201209-2048x1374.png)

## Obtain the Main Account ID

If your account is a main account, you can see the Main Account label and Main Account ID next to the avatar.

![Main Account ID](https://r2.serverless-wordpress.cloud/2024/02/screenshot-20240220-010747-2048x356.png)

Next, you can use [Lougao console](https://console.serverless-wordpress.cloud) to start creating your full-stack Serverless WordPress website.

## Activate required Alibaba Cloud services (You can do this later)

Additionally, Lougao requires Alibaba Cloud's **FC**, **NAS**, and **SLS** services. Therefore, if you haven’t activated these services yet, please activate them first, or you can do so later.

* NAS activation page link: https://nasnext.console.aliyun.com/introduction

* SLS activation page link: https://sls.console.aliyun.com/lognext/open

* FC activation page link: https://fcnext.console.aliyun.com/overview

