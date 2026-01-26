---

# WebEngage / Private SSP Setup Guide

This document outlines the steps required to configure a **Private SSP (Server-Side Provider)** in WebEngage to enable secure server-to-server communication with **CampaignHQ**.
It also explains how to authenticate requests using CampaignHQ API keys.

---

## 1. Creating a Private SSP in WebEngage

### A. Navigate to SSP Configuration

1. Log in to the **WebEngage Dashboard**.
2. Go to **Data Platform** →**Integrations** **SMS** →**PrivateSSP**.
3. Click **Add SSP**.
4. Select **SSP Type** as **Private SSP**.

---

### B. Configure SSP Details

Fill in the following details:

#### SSP

* **Private SSP**

#### Name Your Configuration

* Example: `CampaignHQ Private SSP`
  (You may include environment details like `Prod` or `Staging`.)

#### URL

* Enter the CampaignHQ endpoint that will receive requests from WebEngage.

Example:

```
https://api.campaignhq.co/webengage/ssp
```

> Use the exact endpoint provided by CampaignHQ.

---

### C. Principal Entity ID

#### What is Principal Entity ID?

The **Principal Entity ID** represents the owning business entity or account in WebEngage under which this SSP operates.
It is primarily used in **enterprise or multi-entity WebEngage setups**.

#### When is it required?

* If your WebEngage account has multiple entities or workspaces
* For enterprise or partner-level integrations
* When WebEngage explicitly provides or mandates this value

#### What should you enter?

* If WebEngage has provided a Principal Entity ID → enter it here
* If not provided → **leave this field empty**

> For most standard WebEngage accounts, this field is optional and can be left blank.

---

### D. Add Authorization Header

1. Click **Add Header**.
2. Configure the header as follows:

**Header Key**

```
Authorization
```

**Header Value**

```
<YOUR_CAMPAIGNHQ_API_KEY>
```

This header is required for CampaignHQ to authenticate incoming requests from WebEngage.

---

## 2. Generating API Key in CampaignHQ

### A. Generate API Key

1. Log in to the **CampaignHQ Dashboard**.
2. Go to **Settings** → **Integrations** → **API Keys**
   or visit:
   [https://app.campaignhq.co/settings/integrations/api-keys/](https://app.campaignhq.co/settings/integrations/api-keys/)
3. Click **Generate API Key**.
4. Copy the generated API key.

### B. Use API Key in WebEngage

* Paste the generated API key as the **Authorization** header value while configuring the Private SSP in WebEngage.

> Keep this API key secure. Do not expose it publicly.

---

## 3. Save and Verify

1. Review all the entered details.
2. Click **Add SSP** to save the configuration.
3. The Private SSP is now ready to be used for WebEngage ↔ CampaignHQ integration.

---

## Summary

| Field                | Value                             |
| -------------------- | --------------------------------- |
| SSP Type             | Private SSP                       |
| Configuration Name   | CampaignHQ Private SSP            |
| URL                  | CampaignHQ WebEngage SSP endpoint |
| Principal Entity ID  | Optional                          |
| Authorization Header | CampaignHQ API Key                |

---

If you want next:

* Event payload examples
* Error handling & retries
* WebEngage → CampaignHQ event mapping
* A `/docs/webengage/` folder structure

Just say 👍
