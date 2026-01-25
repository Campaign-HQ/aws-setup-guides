
# AWS / SMS Setup Guide

This document outlines the steps required to configure AWS services to enable SMS through the AWS Social Messaging platform. It also includes the necessary IAM permissions with CampaignHQ.

---

## 1. Creating an IAM User for WhatsApp Messaging

### A. Create a Custom IAM Policy

1. Go to **IAM** → **Policies** → **Create policy**.
2. Select the **JSON** tab and paste the following policy:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "CampaignHQ",
            "Effect": "Allow",
            "Action": [
                "sms-voice:SendVoiceMessage",
                "sms-voice:SendTextMessage",
                "sms-voice:CreateConfigurationSet",
                "sms-voice:CreateEventDestination"
            ],
            "Resource": "*"
        }
    ]
}
```

3. Click **Next**, give the policy a name (e.g., `CampaignHQSMSPolicy`), and create it.

### B. Create the IAM User

1. Go to **IAM** → **Users** → **Add user**.
2. Enter a username (e.g., `campaignhq-sms`).
3. Uncheck **AWS Management Console access**.
4. Proceed to **Permissions** → **Attach policies directly** → Select the policy created above.
5. Complete the user creation process.

### C. Generate Access Keys

1. Open the newly created user and go to the **Security credentials** tab.
2. Under **Access keys**, click **Create access key**.
3. For use case, select **Third-party service**, then click **Next**.
4. Optionally add a description → Click **Create access key**.
5. Save the **Access Key ID** and **Secret Access Key** securely and share them with the CampaignHQ team. You can also download them as a CSV file.
