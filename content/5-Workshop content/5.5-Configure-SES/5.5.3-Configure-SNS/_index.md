---
title : "Configure SNS Notifications"
date : 2024-01-01
weight : 3
chapter : false
pre : " <b> 5.5.3. </b> "
---

In this section, we will configure **Amazon SNS (Simple Notification Service)** to automatically send notification emails (e.g., system alerts, reports) to your Gmail address.

### 1. Create an SNS Topic

1. Go to the **AWS Management Console**, search for **Amazon SNS**, and select **Topics**.
2. Click **Create topic**.
3. Under **Type**, select **Standard**.
4. Enter a **Name** (e.g., dental-system-alerts).
5. Keep the default settings and click **Create topic**.

### 2. Subscribe a Gmail Address to Receive Notifications

Once the Topic is created, we need to add the email address that will receive notifications:

1. On the newly created Topic's detail page, switch to the **Subscriptions** tab and click **Create subscription**.
2. In the **Protocol** field, select **Email**.
3. In the **Endpoint** field, enter your **Gmail** address (e.g., your-email@gmail.com).
4. Click **Create subscription**.

### 3. Confirm the Subscription

1. AWS SNS will send a confirmation email to the Gmail address you entered.
2. Open your Gmail inbox and look for an email titled **AWS Notification - Subscription Confirmation**.
3. Click the **Confirm subscription** link in the email.
4. Return to the AWS Console and verify that the subscription status has changed from *Pending confirmation* to **Confirmed**.

### 4. Publish a Test Message

1. On the Topic page in AWS, click **Publish message**.
2. Enter a **Subject** (e.g., Test Alert from Dental System).
3. Enter content in the **Message body to send to the endpoint** field (e.g., The system is operating normally!).
4. Scroll down and click **Publish message**.
5. Check your Gmail inbox — you should receive the message you just sent.

The SNS system is now ready to be integrated with CloudWatch or the Backend to automatically send notifications.
