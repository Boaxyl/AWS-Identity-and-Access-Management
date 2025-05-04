# AWS-Identity-and-Access-Management

Sure! Here’s the complete write-up I made:

Project Completion Guide
Step 1: Access AWS Management Console
I opened my web browser and navigated to the AWS Management Console. Then, I logged in using my AWS account credentials.

Step 2: Navigate to IAM
I searched for IAM in the AWS console and selected the Identity and Access Management (IAM) service.
Example Image: AWS IAM Dashboard
AWS IAM Dashboard

Step 3: Create IAM Policy
I proceeded to create a custom IAM policy that granted specific permissions.
Screenshot Reference: Selecting EC2 Actions
Selecting EC2 Actions
Steps Taken
- Clicked on Policies in the IAM dashboard.
- Selected "Create Policy".
- Chose EC2 actions to configure appropriate permissions.

Step 4: Define Policy Permissions
I switched to the JSON tab and entered the following policy configuration:
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "ec2:*",
            "Resource": "*"
        }
    ]
}


Example Image: IAM Policy JSON Definition
IAM Policy JSON

Step 5: Review and Create Policy
I named the policy "AllEC2ActionsPolicy", added a description, and clicked "Create Policy".

Step 6: Assign Policy to a User
I attached the newly created policy to an IAM user.
Steps Taken
- Navigated to the Users section in IAM.
- Selected the user Eric.
- Clicked "Add permissions".
- Attached the AllEC2ActionsPolicy to the user.

Step 7: Validate Permissions
To ensure proper functionality, I tested user access to EC2 resources by attempting to perform launch, stop, and terminate actions.
Example Image: Reviewing User Permissions
User Permissions Review

Step 8: Documentation & Final Checks
I documented the IAM setup, including:
- Policy names and configurations.
- User permissions and access control methods.
- Security measures and best practices.
Example Image: IAM Documentation
IAM Documentation


