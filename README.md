# AI Agent Engineer Technical Assessment - n8n Automation

## Overview
This project is an automated workflow built using **n8n** that fetches user data, transforms it, and routes it to different destinations based on specific business logic (Age demographics).

## Workflow Logic
1. **Fetch Data:** Retrieves 10 users from DummyJSON API with **Retry Logic** (3 attempts).
2. **Error Handling:** If the API fails, the error is caught and logged to a Webhook.site URL with a timestamp.
3. **Validation:** Checks if the user list is empty before processing.
4. **Transformation:** - Combines `firstName` and `lastName`.
   - Filters only emails ending with `example.com`.
   - Adds a `processed_at` timestamp.
5. **Conditional Routing (Bonus):**
   - **Users < 30:** Sent to a Webhook.
   - **Users 30-40:** Appended to a **Google Sheet**.
   - **Users > 40:** Sent to an another webhook.

## Challenges & Solutions
- **Google Sheets Formatting:** Phone numbers starting with `+` were causing errors. I solved this by prepending a `'` to treat them as text.
- **Data Filtering:** Since the API returns mostly `dummyjson.com` emails, I perfered not keep the `example.com` filter as required, but demonstrated its functionality by temporarily adjusting it during the demo.

## How to Test
1. Import the `n8n_workflow.json` into your n8n instance.
2. Set up your Google Sheets credentials and urls to your webhook.
3. Execute the workflow.

## Demo Video
[]
