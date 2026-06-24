# Lex Chatbot — Email Fulfillment

![Python](https://img.shields.io/badge/Python-3.8+-blue)
![AWS Lex](https://img.shields.io/badge/AWS-Lex-FF9900?logo=amazonaws&logoColor=white)
![AWS Lambda](https://img.shields.io/badge/AWS-Lambda-FF9900?logo=amazonaws&logoColor=white)
![SES](https://img.shields.io/badge/AWS-SES-FF9900?logo=amazonaws&logoColor=white)

> An **Amazon Lex** chatbot fulfillment layer that sends transactional emails via **AWS SES**, triggered as a **Lambda** function from Lex intent fulfillment.

## Overview

This project implements the fulfillment logic for an Amazon Lex chatbot. When a conversation reaches a point that requires a follow-up email (e.g., a contact request or summary), the Lex bot invokes this Lambda, which composes and dispatches an email through Amazon SES.

## How It Works

```
User ──► Amazon Lex (bot / intents)
              │
        Fulfillment (Lambda)
              │
         sendEmail.py
              │
        Amazon SES ──► recipient inbox
```

## Tech Stack

- **Amazon Lex** — conversational interface / intent routing
- **AWS Lambda** — serverless fulfillment
- **Amazon SES** — email delivery
- **Python (boto3)** — Lambda runtime

## Project Structure

```
└── sendEmail.py    # Lambda handler: parses Lex slots & sends email via SES
```

## How to Deploy

1. Configure an Amazon Lex bot with the relevant intents/slots.
2. Create a Lambda function and upload `sendEmail.py`.
3. Grant the Lambda execution role `ses:SendEmail` permission.
4. Verify sender/recipient emails in Amazon SES.
5. Set this Lambda as the fulfillment hook for your Lex intent.

## Author

**Kuldeep Pal** — [GitHub](https://github.com/kuldeep27396) · [Portfolio](https://www.kuldeep-pal.in/)
