---
title: "Blog 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

# AWS WAF: A SHIELD PROTECTING WEB APPLICATIONS FROM COMMON ATTACKS

When deploying a website or application to the internet, many people often focus on optimizing performance, scaling the system, or improving the user experience.

However, an equally important factor is security.

In reality, web applications are constantly facing numerous threats such as SQL Injection, Cross-Site Scripting (XSS), Bot Traffic, or Distributed Denial of Service (DDoS) attacks. Without proper protection, these attacks can disrupt services, compromise data, and degrade the user experience.

To address this problem, AWS offers the AWS WAF (Web Application Firewall) service, which protects web applications from common threats while allowing for flexible management and construction of security policies.

In practice, AWS WAF is often deployed with Application Load Balancer (ALB), Amazon CloudFront, API Gateway, and AWS Shield to build a multi-layered security system for applications.

KEY FEATURES:

• Protecting applications from common attacks:

AWS WAF can detect and block many common attack types such as SQL Injection, Cross-Site Scripting (XSS), Local File Inclusion, and other malicious requests before they reach the application.

• Create custom security rules:

Users can build custom rules based on IP address, country, HTTP header, URI, or many other conditions to meet the specific security requirements of each system.

• Integrate with multiple AWS services:

AWS WAF can work with Amazon CloudFront, Application Load Balancer (ALB), Amazon API Gateway, and AWS AppSync to protect websites, web applications, and APIs.

• Combine with AWS Shield for DDoS protection:

When deployed with AWS Shield, the system can mitigate the impact of large-scale DDoS attacks. AWS Shield is responsible for network layer protection, while AWS WAF inspects and blocks malicious requests at the application layer.
• Traffic Monitoring and Analysis:

AWS WAF can integrate with Amazon CloudWatch to collect logs, monitor traffic, detect anomalies, and assist administrators in implementing appropriate solutions.

REAL-WORLD SCENARIO:
Suppose an e-commerce website is running a large promotional campaign and has thousands of users accessing it simultaneously.

During this time, an attacker could send a large number of requests containing malicious SQL code or carry out DDoS attacks to disrupt the system.

The deployment architecture is as follows:
User → AWS WAF → Application Load Balancer → EC2 Auto Scaling → Application Web Servers

In this architecture:
<br>&emsp;+ AWS WAF will inspect all requests sent to the system.
<br>&emsp;+ Requests containing malicious code or exhibiting unusual behavior will be blocked at the WAF layer.
<br>&emsp;+ Application Load Balancer distributes legitimate traffic to application servers.
<br>&emsp;+ Auto Scaling automatically scales the number of EC2 instances when traffic increases.
<br>&emsp;+ CloudWatch logs and monitors all system activity.

As a result, the application maintains high availability while protecting user data from common attacks.

CONCLUSION:
What I find impressive about AWS WAF is that it not only functions as a typical web application firewall but can also be combined with many other AWS services to build a comprehensive security system.

In an architecture using AWS WAF in conjunction with Application Load Balancer and EC2 Auto Scaling, AWS WAF acts as the first line of defense, inspecting and filtering all requests before they enter the backend.

When combined with AWS Shield, CloudFront, and CloudWatch, the system can both defend against DDoS attacks and detect and prevent application-layer attacks.

In my opinion, this is a very worthwhile service to learn about when studying AWS because it directly relates to important areas such as Security, Networking, High Availability, and Cloud Architecture.

Through this article, I understand better that security needs to be implemented from the outset, rather than just dealing with incidents when they occur. A good system not only needs to operate stably but also ensure the safety of data and users.

Document link:

https://docs.aws.amazon.com/.../develope.../waf-chapter.html

https://docs.aws.amazon.com/.../aws-waf-and-shield.html

![Picture](/images/3-BlogsPosted/Blog2.jpg)