# Contact Form Email Setup Guide

Your contact form is now ready to send emails! Follow these steps to complete the setup:

## Step 1: Sign Up for EmailJS

1. Go to [emailjs.com](https://www.emailjs.com/)
2. Click **"Sign Up Free"** and create an account
3. Verify your email

## Step 2: Create an Email Service

1. After logging in, go to **"Email Services"** in the left sidebar
2. Click **"Add Service"**
3. Choose **"Gmail"** (or your email provider)
4. Connect your email account (saichaithanyakummari@gmail.com)
5. Complete the verification process
6. **Copy your Service ID** - you'll need it in Step 4

## Step 3: Create an Email Template

1. Go to **"Email Templates"** in the left sidebar
2. Click **"Create New Template"**
3. Name it something like `portfolio_contact`
4. Configure the template with these fields:

   **Template content example:**

   ```
   Subject: New message from {{from_name}}

   From: {{from_email}}
   Message:
   {{message}}
   ```

5. In the template settings:
   - **To email:** saichaithanyakummari@gmail.com
   - Keep other fields as default

6. **Copy your Template ID** - you'll need it in Step 4

## Step 4: Get Your Public Key

1. Go to **"Account"** in the left sidebar
2. Click on **"API Keys"**
3. **Copy your Public Key**

## Step 5: Update Your HTML File

Open `index.html` and find these two lines in the JavaScript section (around line 235):

```javascript
emailjs.init("YOUR_PUBLIC_KEY_HERE");
```

and

```javascript
emailjs.send(
  "service_YOUR_SERVICE_ID",
  "template_YOUR_TEMPLATE_ID",
  emailParams,
);
```

Replace:

- `YOUR_PUBLIC_KEY_HERE` → Your actual Public Key from Step 4
- `service_YOUR_SERVICE_ID` → Your actual Service ID from Step 2 (keep the "service\_" prefix)
- `template_YOUR_TEMPLATE_ID` → Your actual Template ID from Step 3 (keep the "template\_" prefix)

**Example:**

```javascript
emailjs.init("k8f7g9h2j4k6l8m0n");
emailjs.send("service_1a2b3c4d5e", "template_9z8y7x6w5v", emailParams);
```

## Step 6: Test Your Form

1. Save the HTML file
2. Open your portfolio in a browser
3. Scroll to the Contact section
4. Fill in the form and click "Send Message"
5. You should receive an email at saichaithanyakummari@gmail.com

## Troubleshooting

- **Form not sending:** Check that your Public Key, Service ID, and Template ID are correct
- **Email not received:** Check Gmail spam folder
- **Check browser console:** Press F12 and look at the Console tab for error messages

## Important Notes

- The free tier of EmailJS allows 200 emails/month - perfect for a portfolio
- Your Public Key is safe to share (it's public), but keep your Service ID and Template ID private
- Make sure CORS is enabled in EmailJS settings if you experience cross-origin errors

## Need Help?

EmailJS documentation: [emailjs.com/docs](https://www.emailjs.com/docs)
