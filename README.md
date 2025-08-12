# Setting_Up_Secure_Authentication_AWS_API 

# Step 1 — Create IAM Role
1. In AWS Console, go to IAM → Roles → Create role.
![create-role](./New-Pic-22/1.create-role.png)

2. Trusted entity type: Select AWS service.
![select-trusted-entity-type](./New-Pic-22/2.select-trusted-type.png)

3. Use case: Choose EC2 (since your script will interact with AWS services).
![use-case-ec2](./New-Pic-22/3.use-case-ec2.png).

4. Click Next and skip attaching permissions for now (we’ll attach later).

5. Name it and Click Create role.

# Step 2 — Create IAM Policy
1. Go to IAM → Policies → Create policy.
![IAM-Policy](./New-Pic-22/5.IAM-policy.png)

2. Choose visual.
![set-iam-policy](./New-Pic-22/6.set-iam-policy.png).

3. select all resources and click next.
![select-resources](./New-Pic-22/7.select-resources.png)

4. Name the policy and click create policy.

# Step 3 — Create IAM User
1. Go to IAM → Users → Create user.
![iam-user](./New-Pic-22/9.iam-user.png)

2. User name: automatation user.
![name-user](./New-Pic-22/10.name-user.png)

3. Access type: Check Programmatic access (for AWS CLI). Click Create user.

# Step 4 — Assign User to IAM Role
1. Go to IAM → Users → Click automation_user.
![assign-role](./New-Pic-22/12.Assign-role.png)

2. Click Add permissions.
![set-permission](./New-Pic-22/13.set-permission.png)
3. Select Attach policies directly.

4. Search for my-project-policy (the same one the role has).
![select-policy](./New-Pic-22/14.select-policy.png)

5. Check the box, click Next, then Add permissions.

Now the user and the role both have the same access.

# Attach the IAM Policy to the User
1. Go to Users → automation_user.
![attach-policy](./New-Pic-22/15.Attach-policy.png)

2. Permissions → Add permissions → Attach policies directly.
![add-permission](./New-Pic-22/16.add-permission.png).

3. Select EC2_S3_FullAccess_Policy and Save.
![select-ec2-s3](./New-Pic-22/17.select-ec2-s3.png)

#  Create Programmatic Access Credentials
1. Go to Users → automation_user.
![Programatic-access](./New-Pic-22/18.programatic-access.png).

2. Security credentials → Create access key.
![create-access](./New-Pic-22/19.Create-access.png)

3. Choose Command Line Interface (CLI) as the use case.
![cli](./New-Pic-22/20.CLI.png).

4. Copy:
Access Key ID
Secret Access Key (only shown once — store it securely).
![created](./New-Pic-22/21.CREATED.png).

# Configure AWS CLI on Linux
1. on your terminal, enter aws configure.

2. enter your credential 
![cinfigure-aws](./New-Pic-22/22.terminal.png).

3. verify if aws is configured.
![testing](./New-Pic-22/23.testing.png).