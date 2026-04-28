# AWS Security Internship – Internee.pk
---

- AWS cloud security project using IAM roles, WAF for ALB protection, CloudTrail and CloudWatch logging, multi-region backups, and AWS Open Data ingestion into S3 to demonstrate secure, monitored, and resilient cloud infrastructure practices.
---

## Internship Deliverables

### 1. **Billing & Budgeting**

Set up **AWS Budgets** to enforce strict cost controls.

- Created a budget named `hard budget` with a $1.00 threshold.
- Verified account billing shows **$0.00** under free tier.

<img width="1000" height="600" alt="budget" src="https://github.com/user-attachments/assets/409e1b28-2283-4e14-afd3-66f19464db69" />

  
*Context: Shows budget health status as Healthy with $1.00 threshold.*


<img width="1000" height="600" alt="budget-billing" src="https://github.com/user-attachments/assets/43da64da-7e6b-463b-b393-54b16ff7b4db" />


*Context: Displays April 2026 billing period with $0.00 charges.*

---

### 2. **IAM Dashboard**

Reviewed IAM dashboard for account security posture.

- Highlighted recommendations (MFA for root user).
- Verified IAM resources (roles, groups, policies).

<img width="1000" height="600" alt="iam-dashboard" src="https://github.com/user-attachments/assets/b670862b-2eef-4e36-8fee-a7c3257f11f4" />


*Context: Shows IAM security recommendations and account overview.*

---

### 3. **IAM User Details**

Configured IAM user `admin-user`.

- Attached `AdministratorAccess` and `IAMUserChangePassword` policies.
- Enabled console access.

<img width="1000" height="600" alt="iam-admin-user" src="https://github.com/user-attachments/assets/927aa202-65da-4418-9976-659e1fe82af6" />

*Context: Displays `admin-user` with attached policies and console access enabled.*

---

### 4. **Admin User Security Credentials**

Secured root account with MFA.

- Assigned virtual MFA device.
- Verified no active access keys.

<img width="1000" height="600" alt="iam-user-details" src="https://github.com/user-attachments/assets/acb27065-5f73-4ba6-a2ba-e7daf80e197e" />


*Context: Confirms MFA enabled for root account with no active access keys.*

---

### 5. **User Groups**

Created IAM groups for role-based access control.

- Groups: Admins, Auditors, Developers.
- Applied least-privilege permissions.

<img width="1000" height="600" alt="iam-user-groups" src="https://github.com/user-attachments/assets/c57616fd-c2b3-4c33-b0d5-37af2af2c08b" />


*Context: Shows Admins, Auditors, Developers groups created with defined permissions.*

---

### 6. **EC2 Instance – SSH & Nginx**

Launched and hardened EC2 instance `secure-server`.

- Installed Apache2 and Nginx.
- Verified DNS resolves to public webpage.

<img width="1000" height="600" alt="instance-2" src="https://github.com/user-attachments/assets/d6b20d80-e06e-4e72-9ed4-29d97ff65b4f" />


*Context: Displays instance metadata (public/private IPs, AMI, VPC, subnet).*

<img width="1000" height="600" alt="dns-webpage" src="https://github.com/user-attachments/assets/66a0eb59-0f6c-4891-a372-5be79baec662" />


*Context: Confirms successful Apache2 installation with default Ubuntu page.*

<img width="1000" height="600" alt="ssh-nginx" src="https://github.com/user-attachments/assets/97797252-f550-41a8-b4a1-551bdc104ba9" />
<img width="1000" height="600" alt="ssh-nginx-2" src="https://github.com/user-attachments/assets/abab4d2e-838c-4c94-807d-ad401a434423" />


*Context: Shows Nginx running and serving the default welcome page.*

---

### 7. **CloudTrail – Main Trail**

Configured **CloudTrail** for auditing.

- Enabled multi-region trail `internship-trail`
- Captures management events (read/write)
- Logs stored securely in S3 with encryption

<img width="1000" height="600" alt="cloudtrail-main" src="https://github.com/user-attachments/assets/7ce3b668-05cd-4f98-b9d0-2e77ca6eeef7" />


*Context: Shows `main-trail` enabled with multi-region logging and S3 delivery.*

---

### 8. **S3 Buckets**

Created dedicated S3 buckets for logs and backups.

- Buckets: `aws-cloudtrail-logs`, `backup-bucket`, `second-bucket`.

<img width="1000" height="600" alt="s3-buckets" src="https://github.com/user-attachments/assets/266bed10-51d3-49e9-aa0c-cc85c5dd4a3f" />


*Context: Shows multiple buckets created in `us-east-2` for redundancy.*

---

### 9. **AWS Config**

Enabled **AWS Config** for compliance tracking.

- Configured recording strategy for all resource types.
- Applied managed rules for certificates and ALBs.

<img width="1000" height="600" alt="aws-config-settings" src="https://github.com/user-attachments/assets/2cee5cab-e0c0-45c2-8887-6cdda64140e0" />


*Context: Shows recording strategy, IAM role, and S3 delivery channel setup.*


<img width="1000" height="600" alt="aws-config-rules" src="https://github.com/user-attachments/assets/92ad0edf-7bbd-4491-ab2c-b6626b5a12b3" />


*Context: Displays managed rules like certificate expiration checks and ALB header validation.*

---

### 10. **Web ACL Creation**

Created **WAF Web ACL** (`internship-waf`).

- Applied managed rules (Bad Inputs, SQLi, Reputation List).
- Configured overrides for specific attack vectors.

<img width="1000" height="600" alt="web-acl-create" src="https://github.com/user-attachments/assets/3a244b29-713a-4366-aaba-eff42e9012c7" />


*Context: Shows ACL setup with recommended rules and overrides.*

<img width="1000" height="600" alt="web-acl" src="https://github.com/user-attachments/assets/177e0b54-2ee6-46ac-925e-653c6825eec2" />


*Context: Displays `UpdateWebACL` event with user identity, source IP, and JSON request parameters.*


---

### 11. **CloudWatch Logs**

Integrated WAF logs into CloudWatch.

- Created log group `aws-waf-logs-internship`.
- Verified JSON-formatted logs with rule IDs.

<img width="1000" height="600" alt="cloudwatch-logs" src="https://github.com/user-attachments/assets/1e1e3f16-cc78-405c-a520-3f36647c67c6" /> 


*Context: Shows WAF log events with terminating rule IDs and request metadata.*

---

### 12. **WAF Dashboard**

Monitored WAF activity via dashboard.

- Visualized ALLOW vs BLOCK traffic.
- Tracked rule effectiveness.

<img width="1000" height="600" alt="waf-dashboard-1" src="https://github.com/user-attachments/assets/344f24da-3138-476b-bb5a-163bdbb4ec0d" />
<img width="1000" height="600" alt="waf-dashboard-2" src="https://github.com/user-attachments/assets/aabf1795-6697-45fc-b3b6-9de8d320da77" />
<img width="1000" height="600" alt="waf-dashboard-3" src="https://github.com/user-attachments/assets/dfdc2e94-7a84-4d67-92b1-a6c7ad523e35" />

*Context: Shows request activity trends and rule metrics for `internship-waf`.*

---

### 13. **CloudTrail Event History**

Reviewed CloudTrail event logs for auditing.

- Captured events like `StartInstances`, `ConsoleLogin`, `UpdateWebACL`.
- Verified user and service activity.

<img width="1000" height="600" alt="cloudtrail-events" src="https://github.com/user-attachments/assets/cdea5ec0-59ce-4a47-a601-ebdac7392d8f" />


*Context: Displays detailed event logs with timestamps, sources, and resource IDs.*


---

### 14. **Backup Snapshot**

Created **EBS snapshot** for EC2 instance volume.

- Snapshot ID: `snap-01bb57a31fcd6a9d2`.
- Size: 8 GiB.
- Status: Completed.

<img width="1000" height="600" alt="backup-1" src="https://github.com/user-attachments/assets/3aeaf91a-b642-4813-b73b-e33196399b3c" />


*Context: Shows `internship-backup-1` snapshot completed with 100% progress.*

---

### 15. **Backup Copy in Another Region**

Copied snapshot to another AWS region for redundancy.

- Snapshot ID: `snap-01bfcf1d7df158783`.
- Name: `internship-backup-copy`.
- Status: Completed.
  
<img width="1000" height="600" alt="backup-copy" src="https://github.com/user-attachments/assets/770a1cc4-0d12-4acf-9256-ca532ff25147" />


*Context: Shows snapshot successfully copied to another region with full completion.*

---

### 16. **IAM Users**

IAM Findings

- Initial setup used broad admin privileges
- Identified as security risk (principle of least privilege violated)

Improvements implemented

- Created IAM role for EC2
- Attached minimal required permissions
- Reduced direct dependency on admin user

Reviewed IAM users for secure access.

- User: `admin-user`.
- Console access enabled.
- Attached policies: `AdministratorAccess`, `IAMUserChangePassword`.

<img width="1000" height="600" alt="iam-users" src="https://github.com/user-attachments/assets/e8427c8d-01c5-4124-9dd4-7e5d5c60ba81" />


*Context: Displays `admin-user` summary with attached policies and access key info.*

---

### 17. **IAM Role Policies**

Configured IAM role for EC2 instance.

- Role: `EC2-Secure-Role`.
- Policies attached: `AmazonSSMManagedInstanceCore`, `CloudWatchAgentServerPolicy`.
- Trust relationship allows EC2 to assume role.

<img width="1000" height="600" alt="role-policies" src="https://github.com/user-attachments/assets/9b46ff46-fa48-492f-a3c7-ddcaaf869f86" />


*Context: Shows role summary, ARN, and attached policies.*

---

### 18. **Instance Summary with IAM Role**

Verified EC2 instance configuration with IAM role attached.

- Instance ID: `i-0c76af6336b0353b4`.
- Role: `EC2-Secure-Role`.
- Public IP: `18.189.1.125`.
- Running state confirmed.

<img width="1000" height="600" alt="instance-summary" src="https://github.com/user-attachments/assets/ab7a2fe8-2bd4-4ac2-b120-0c527e6a2197" />


*Context: Displays instance metadata with IAM role attached.*

---

### 19. **CloudShell – Public Dataset Integration**

Used AWS CLI in CloudShell to copy public datasets.

- Source: `covid19-lake` (AWS Open Data).
- Destination: `mariya-open-data-project`.
- Verified dataset (`us_daily.csv`) copied successfully.

<img width="1000" height="600" alt="cloudshell-dataset" src="https://github.com/user-attachments/assets/e90c8b64-0994-4cdd-8dd7-191a6b1ed645" />


*Context: Shows CLI commands copying COVID-19 dataset into personal S3 bucket.*

---

## Summary of Security Measures Implemented

- Billing controls enforced with budgets.
- IAM secured with MFA, groups, users, and least privilege.
- EC2 hardened with Apache2/Nginx and IAM role.
- CloudTrail enabled for auditing.
- S3 buckets created for logs/backups.
- AWS Config compliance rules applied.
- WAF ACL deployed with managed rules.
- CloudWatch logs integrated for monitoring.
- Snapshots created and copied cross-region.
- Public datasets ingested into S3 for analysis.
