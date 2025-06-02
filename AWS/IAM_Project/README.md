# AWS IAM Role & Policy Project

## 📌 Objective
Create and attach an IAM Role to an EC2 instance to allow S3 ReadOnly access without using Access Keys.

## 🔧 Tools Used
- AWS IAM
- EC2
- S3
- AWS CLI

## ✅ Steps Performed

1. **Create IAM Policy**
   - Go to IAM → Policies → Create Policy
   - Choose `S3 ReadOnlyAccess` JSON
   - Name it: `S3ReadOnlyPolicy`

2. **Create IAM Role**
   - IAM → Roles → Create Role
   - Select EC2 as trusted entity
   - Attach `S3ReadOnlyPolicy`
   - Name it: `EC2S3ReadOnlyRole`

3. **Launch EC2 Instance**
   - EC2 → Launch Instance
   - In **Step 3 (Configure Instance)**, select IAM Role: `EC2S3ReadOnlyRole`

4. **Verify Access from EC2**
   - Connect to EC2 via SSH
   - Run: `aws s3 ls`
   - ✅ You should see list of buckets if S3 access is working

## 📸 Screenshot (optional)
Add a screenshot of IAM role attached to EC2 or S3 access from EC2 here.

## 📝 Learnings
- IAM Policies vs Roles
- Role attachment to EC2
- Secure service-to-service communication without credentials
