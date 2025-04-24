# 📬 Serverless Contact Form API 

![AWS Cloud](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Lambda](https://img.shields.io/badge/Lambda-FF9900?style=for-the-badge&logo=aws-lambda&logoColor=white)
![API Gateway](https://img.shields.io/badge/API_Gateway-C925D1?style=for-the-badge)
![S3](https://img.shields.io/badge/S3-569A31?style=for-the-badge&logo=amazon-s3&logoColor=white)
![CloudFront](https://img.shields.io/badge/CloudFront-232F3E?style=for-the-badge)
![Route53](https://img.shields.io/badge/Route53-8C4FFF?style=for-the-badge)

🔗 **Not Live:** [https://ph2l1xbzrf.execute-api.us-east-1.amazonaws.com/prod/form](https://ph2l1xbzrf.execute-api.us-east-1.amazonaws.com/prod/form)(Note: This endpoint was active during development but has been decommissioned to avoid AWS charges. The screenshots demonstrate the working functionality.)

## 📋 Project Overview

This project builds a secure, serverless contact form API using AWS Lambda and API Gateway. The API is wired to a static front-end hosted on Amazon S3 and secured via CloudFront and ACM, with DNS routing via Route 53 to the custom subdomain `form.deployjimmy.com`.

---

## ✅ Key Features & Services

- ☁️ **AWS Lambda** – Lightweight backend for contact form processing
- 🌐 **API Gateway (HTTP API)** – REST-style endpoint at `/form`
- 🔐 **Amazon Certificate Manager** – Enforces HTTPS encryption
- 📦 **Amazon S3** – Hosts the static site front-end
- 🧭 **Route 53** – DNS routing for `form.deployjimmy.com`
- 🚀 **CloudFront** – Secures and accelerates API endpoint traffic
- 🛠️ **Manual Deployment** – Built and debugged without automation to showcase end-to-end understanding
 
---

## 📁 Project Structure

```bash
aws-s3-lambda-api-contactform/
├── architecture/              # AWS architecture diagram (PNG)
│   └── aws-contact-form-architecture.png  # Architecture diagram
├── lambda/                    # Node.js Lambda function (API logic)
│   ├── index.js               # Lambda handler
│   └── package.json           # Dependencies
├── static-site/               # Contact form HTML and optional CSS styling
│   ├── index.html             # Form interface
│   └── style.css              # Styling
├── docs/                         # Additional documentation
│   └── logical-flow.md           # Detailed logical flow explanation
├── LICENSE
└── README.md
```

---

## 🗺️ Architecture Diagram

![Architecture Diagram](architecture/aws-contact-form-architecture.png)

> 📌 *Diagram depicts HTTPS-secured traffic flow from user browser to CloudFront → API Gateway → Lambda, with DNS routing via Route 53.*

---

## 🛠 Deployment Steps

1. **Lambda Function Setup**
   - Created Node.js Lambda function with appropriate IAM role
   - Implemented form processing logic with input validation
   - Configured memory allocation and timeout settings
   - Tested function using the AWS Lambda console

2. **API Gateway Configuration**
   - Created HTTP API with `/form` resource path
   - Set up POST method integration with Lambda function
   - Configured CORS headers for frontend integration
   - Deployed API to production stage

3. **Frontend & Security Configuration**
   - Created S3 bucket for static form hosting
   - Configured CloudFront distribution with ACM certificate
   - Set up Route 53 record to point to CloudFront
   - Verified end-to-end functionality

---

## 💡 Usage

To test the API directly:

```bash
curl -X POST "https://ph2l1xbzrf.execute-api.us-east-1.amazonaws.com/prod/form" \
  -H "Content-Type: application/json" \
  -d '{"name": "Jimmy", "email": "jimmy@example.com", "message": "Test from CLI"}'
```

Expected response:

```json
{ "message": "CommonJS Lambda now works!" }
```

---

## 🧠 Skills Demonstrated

- Serverless architecture design and implementation
- Lambda function development and debugging
- API Gateway routing and CORS configuration
- IAM role management and security best practices
- HTTPS and SSL certificate provisioning
- CloudFront CDN configuration
- Route 53 custom domain setup
- Front-end to back-end integration
- Infrastructure troubleshooting in WSL and Windows environments

---

## 🔄 Related Projects

- [Static Website Deployment](https://github.com/jimmyperalta-dev/aws-ec2-s3-route53-webapp)
- [EC2 Metrics Dashboard](https://github.com/jimmyperalta-dev/aws-ec2-monitoring-dashboard)

---

## </> Development Notes

This project was developed with assistance from AI tools like Claude to code and enhance documentation quality. All implementations were validated and tested by me.

---

## 👤 Author

**Jimmy Peralta**  
🛠️ Associate Media Systems Engineer | ☁️ AWS Cloud Enthusiast  
🌐 [https://www.deployjimmy.com](https://www.deployjimmy.com)
