# Gmail Email Validation Automation 📧

## 📌 Project Overview

The **Gmail Email Validation Automation** is a simple email validation system built using **n8n workflow automation**.

The workflow receives incoming email information through a Webhook and checks whether the email address contains `@gmail.com`.

Using conditional IF logic, the workflow automatically separates incoming email addresses into two branches:

- **TRUE:** If the email address contains `@gmail.com`.
- **FALSE:** If the email address does not contain `@gmail.com`.

Finally, the workflow returns an appropriate response through the Respond to Webhook node.

## 🎯 Project Objective

The main objective of this project is to automate email domain checking and reduce manual verification.

It demonstrates how webhooks, conditional logic, and automated responses can be combined to build a simple email validation system.

## ⚙️ Technologies Used

- **n8n:** Workflow automation platform.
- **Webhook:** Receives incoming email data.
- **IF Node:** Checks whether the email contains the specified domain.
- **Edit Fields Node:** Prepares the output response.
- **Respond to Webhook:** Returns the validation result.

## 🔄 Workflow Architecture

```text
       Incoming Email
              |
              v
           Webhook
              |
              v
          IF Condition
              |
        +-----+-----+
        |           |
      TRUE         FALSE
        |           |
        v           v
    Edit Fields   Edit Fields
        |           |
        v           v
    Respond       Respond
    to Webhook    to Webhook
        |           |
        v           v
   Gmail Domain   Other Domain
     Detected      Detected
```

## 🧠 How It Works

**Step 1: Webhook Trigger**

The workflow receives incoming email information through an HTTP POST request.

**Step 2: IF Condition**

The IF node checks whether the incoming email address contains `@gmail.com`.

**Step 3: TRUE Branch**

If the email address contains `@gmail.com`, the workflow follows the TRUE branch.

**Step 4: FALSE Branch**

If the email address does not contain `@gmail.com`, the workflow follows the FALSE branch.

**Step 5: Automated Response**

The Edit Fields node prepares the output, and the Respond to Webhook node sends the result back to the requester.

## 📊 Example Results

### Example 1: Gmail Address

Input:

```json
{
  "email": "example@gmail.com"
}
```

Output:

```json
{
  "email": "example@gmail.com",
  "result": true,
  "message": "Gmail domain detected"
}
```

### Example 2: Non-Gmail Address

Input:

```json
{
  "email": "example@yahoo.com"
}
```

Output:

```json
{
  "email": "example@yahoo.com",
  "result": false,
  "message": "Gmail domain not detected"
}
```

## 🚀 Key Features

- Automated email domain checking.
- Webhook-based input processing.
- Conditional TRUE/FALSE classification.
- Separate processing branches.
- Automated HTTP responses.
- Simple and efficient workflow design.

## 🛠️ Setup Instructions

1. Create an account or log in to n8n.
2. Import the exported workflow JSON file.
3. Open the Webhook node.
4. Configure the webhook method and path.
5. Configure the IF node to check whether the email field contains `@gmail.com`.
6. Configure both Edit Fields nodes.
7. Configure the Respond to Webhook nodes.
8. Test the workflow using different email addresses.
9. Activate or publish the workflow.

## 🔮 Future Improvements

- Support multiple email domains.
- Validate email address format.
- Detect suspicious email domains.
- Integrate AI-powered spam detection.
- Connect directly with Gmail.
- Store validation history in Google Sheets.
- Generate email validation reports.

## 🔐 Important Note

This project performs email domain checking only.

An email address containing `@gmail.com` is not necessarily safe or legitimate. Similarly, an email address from another domain is not necessarily spam.

This workflow does not currently perform spam detection, phishing detection, or sender verification.

## 👨‍💻 Author

Chiliveru Meghana

AI Automation | n8n | Workflow Development

## ⭐ Conclusion

This project demonstrates the practical implementation of webhook-based automation and conditional logic using n8n.

It provides a foundation for developing more advanced email validation and AI-powered email security systems.

If you find this project useful, consider giving the repository a ⭐.
