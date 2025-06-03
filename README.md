
# 🚀 My AWS Infrastructure with Terraform Modules – A Complete Guide

## 🌐 Introduction

As a DevOps and cloud infrastructure, I recently completed my hands-on project deploying a scalable, modular infrastructure on **Amazon Web Services (AWS)** using **Terraform**.

---

## 🧱 Project Overview

This project provisions:

- A **VPC** with a public subnet
- An **EC2 instance** behind an **Application Load Balancer**
- A **RDS MySQL** database
- An **S3 bucket** for storage
- Modularized Terraform code

---

## 🧭 Architecture Diagram


```
             ┌────────────┐
             │    S3      │
             └────┬───────┘
                  │
           ┌──────▼──────┐
           │    VPC      │
           └────┬───────┬┘
                │       │
         ┌──────▼───┐   ▼────────┐
         │  Subnet  │           │
         └────┬─────┘           │
              ▼                 ▼
         ┌────────┐       ┌────────┐
         │   ALB  ├──────►│  EC2   │
         └────────┘       └────────┘
              │
              ▼
           ┌──────┐
           │ RDS  │
           └──────┘
```

---

## 📁 Terraform Modules

Each component is isolated in its own module:

- `/modules/vpc`
- `/modules/ec2`
- `/modules/alb`
- `/modules/rds`
- `/modules/s3`

This encourages **code reusability**, **clarity**, and **modular scaling**.

---

## ⚙️ How to Deploy It

1. **Install Terraform and AWS CLI**
2. Configure AWS credentials with `aws configure`
3. Unzip the project and edit variables:
   ```bash
   unzip my-first-aws-infra-final.zip
   cd my-first-aws-infra
   ```
4. Create a `terraform.tfvars`:
   ```hcl
   key_name       = "my-key"
   db_password    = "Secure1234!"
   s3_bucket_name = "unique-bucket-name"
   ```
5. Deploy with:
   ```bash
   terraform init
   terraform apply
   ```

---

## 🔁 Cleanup

```bash
terraform destroy
```

## 💡 Lessons Learned

- **Terraform Modules** keep infrastructure organized
- **Outputs** make integrating components easier
- Working with real AWS services helps reinforce theory

---

## ☁️ What's Next?

- Add a **Route53 domain**
- Enable **HTTPS with ACM**
- Add **CloudWatch monitoring**
- Automate with **CI/CD**


---

## 🎯 Final Thoughts

Starting with Terraform can be intimidating, but once you modularize and apply incrementally, it becomes powerful and intuitive. I hope this guide gives you a head start in your cloud infrastructure journey!
