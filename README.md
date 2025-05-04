# AWS-Identity-and-Access-Management

Certainly! Below is your revised **Step-by-Step Guide**, incorporating **IAM best practices**, **group-based access management**, and **clarified policy configurations** while ensuring security and completeness.

```markdown
# **AWS IAM Project Completion Guide**

## **Step 1: Access AWS Management Console**
1. Open a web browser.
2. Navigate to the **AWS Management Console**.
3. Log in using your **AWS account credentials**.

## **Step 2: Navigate to IAM**
1. Search for **IAM** in the AWS console.
2. Click on **Identity and Access Management (IAM)**.

Example Image: AWS IAM Dashboard  
*(Insert relevant screenshot here)*

## **Step 3: Create "Development-Team" Group and Add Users**
1. In **IAM**, go to **User groups**.
2. Click **Create group**.
3. Enter the group name: `Development-Team`.
4. Under **Users**, select **Jack** and **Ade**.
5. Click **Create group** to finalize.

## **Step 4: Create IAM Policy for EC2 and S3 Access**
1. Navigate to **IAM** > **Policies** > **Create policy**.
2. Select **JSON** editor.
3. Enter the following policy to grant specific EC2 and S3 permissions:
   
   ```json
   {
       "Version": "2012-10-17",
       "Statement": [
           {
               "Effect": "Allow",
               "Action": [
                   "ec2:DescribeInstances",
                   "ec2:StartInstances",
                   "ec2:StopInstances",
                   "s3:ListBucket",
                   "s3:GetObject"
               ],
               "Resource": [
                   "arn:aws:ec2:region:account-id:instance/*",
                   "arn:aws:s3:::specific-bucket-name/*"
               ]
           }
       ]
   }
   ```
4. Click **Next**.
5. Name the policy: `"EC2-S3-Access-Policy"`, add a description, and click **Create policy**.

Example Image: IAM Policy JSON Definition  
*(Insert relevant screenshot here)*

## **Step 5: Attach the Policy to "Development-Team"**
1. In **IAM**, navigate to **User groups**.
2. Select `"Development-Team"`.
3. Click **Attach policies**.
4. Search for **EC2-S3-Access-Policy**.
5. Select the policy and click **Attach policy**.

## **Step 6: Implement IAM Best Practices**
✅ **Principle of Least Privilege**:  
   - The policy only grants necessary actions to reduce security risks.  
✅ **Restrict `"Resource": "*"` Usage**:  
   - Instead of `"*"` (allowing all resources), specific ARNs are defined for controlled access.  
✅ **Use Groups Instead of Individual Assignments**:  
   - Policies are assigned to a group (`Development-Team`) rather than individual users, improving scalability.

## **Step 7: Validate Permissions**
1. Navigate to **IAM** > **User groups**.
2. Confirm **Jack** and **Ade** are members of **Development-Team**.
3. Ensure the attached policy grants appropriate **EC2 and S3 permissions**.
4. Test access by attempting **start/stop EC2 instances** and **retrieving objects from S3**.

Example Image: Reviewing User Permissions  
*(Insert relevant screenshot here)*

## **Step 8: Documentation & Final Checks**
Ensure the following are properly documented:
- Policy configurations and assigned permissions.
- IAM best practices applied.
- Security measures implemented.
- Screenshots of each major step for clarity.

Example Image: IAM Documentation  
*(Insert relevant screenshot here)*  




