# Phishing Email Analysis Toolkit

## Sample Phishing Email

```
Subject: Important Registration Required - Immediate Action Needed

Dear Candidate,

We are pleased to inform you that you have been shortlisted for an opportunity with XXX Corporation. To proceed, please visit our official site or complete the registration form using the link below:

https://forms.gle/rGd246s8GfcdrCyv9

Upon registration, you will receive:

1) Confirmation letter
2) Access to resources
3) Assigned tasks
4) Completion certificate
5) Ongoing support and communication

Please ensure registration within 24 hours to avoid losing this opportunity. For assistance, contact the number below.

Thanks and Regards,

John Doe
Program Coordinator
XXX Corporation
Mobile No. - 98XXXXXXX7
```

## Phishing Indicators Identified

| Indicator Type         | Description                                                                        |
| ---------------------- | ---------------------------------------------------------------------------------- |
| **Sender Spoofing**    | The email may appear to come from a legitimate source, but verification fails.     |
| **Suspicious Link**    | The link uses a Google Form, which could be used for phishing data collection.     |
| **Urgency & Pressure** | Encourages user action with vague promises and urgency.                            |
| **Grammar Issues**     | Unnatural phrasing like "completion certificate" without context raises suspicion. |

## Using MXToolbox's Header Analyzer

Steps to extract and analyze email headers:

1. **Open the Email** in Gmail (or your email client).
2. Click the **three dots (⋮)** next to the reply button and select **\<Show original\>**.
3. Click **"Copy to clipboard"** to copy the full header.
4. Open [MXToolbox Email Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx).
5. Paste the copied header and click **"Analyze Header"**.

## Authentication Results Summary

| Check                  | Status          | Implication                                                                    |
| ---------------------- | --------------- | ------------------------------------------------------------------------------ |
| **DMARC**              | ❌ Not Compliant | Indicates SPF or DKIM failed or are not aligned; lowers trust.                 |
| **SPF Alignment**      | ✅ Passed        | Sending IP authorized; properly aligned.                                       |
| **SPF Authenticated**  | ✅ Passed        | Sender IP verified as legitimate.                                              |
| **DKIM Alignment**     | ✅ Passed        | Domain in DKIM signature matches From domain.                                  |
| **DKIM Authenticated** | ❌ Failed        | Body/content may have been modified post-signing—suggests potential tampering. |

## Screenshots of the report
![MXToolbox Header Analysis Output](images/mxtoolbox-result.png)
![MXToolbox Header Analysis Output](images/mxtoolbox-result.png)
