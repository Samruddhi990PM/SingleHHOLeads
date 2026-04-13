# 📘 Lead Capture App – Strategy Cues

## 📌 Overview

This application is designed to capture leads from **Single Holiday Home Owners** and provide them with two immediate engagement options:

1. Reach out via WhatsApp
2. Schedule a call via Calendly

The app focuses on simplicity, fast onboarding, and seamless lead capture.

---

## 🚀 Features

* Clean SaaS-style UI for lead capture
* Simple form to collect user details
* Data storage using Supabase
* Instant post-submission actions:

  * WhatsApp redirection
  * Calendly scheduling

---

## 🧩 Tech Stack & Flow

### 1. Lead Capture (Form 1)

* Built using HTML
* Collects:

  * Name
  * Contact Number

➡️ On submission:

* Data is sent and stored in Supabase database

---

### 2. Engagement Options (Form 2)

After successful submission, users are presented with:

* Option to initiate WhatsApp conversation
* Option to book a meeting via Calendly

---

## ⚙️ Configuration

The application uses the following hardcoded configuration:

```js
const CONFIG = {
  SUPABASE_URL:      "https://bkmqdlkafkaq.supabase.co",
  SUPABASE_ANON_KEY: "_ANON_KEY",
  WHATSAPP_NUMBER:   "9999988888",
  CALENDLY_URL:      "https://calendly.com/Tejas-official990/30min",
};
```

---

## 🗄️ Database Setup (Supabase)

### Table Structure (Example: `leads`)

Account: ishanstrategycues
Table path: accountonboarding -> SCGenericApps -> leads

| Column Name    | Type      |
| -------------- | --------- |
| id             | uuid (PK) |
| name           | text      |
| contact_number | text      |
| created_at     | timestamp |

### Required RLS Policy

To allow public form submissions, run:

```sql
ALTER TABLE leads ENABLE ROW LEVEL SECURITY;

CREATE POLICY "Allow public insert"
ON leads
FOR INSERT
TO anon
WITH CHECK (true);
```

---

## 🔄 Application Flow

1. User clicks on ad
2. Lands on lead capture page
3. Enters Name & Contact Number
4. Data is stored in database
5. User is redirected to:

   * WhatsApp chat
     **or**
   * Calendly booking page

---

## 🔄 GIT and Vercel locations
Push this repo to GitHub: Samruddhi990PM -> PriceLabsDeviationAnalyzer

Vercel: samruddhi.waghchaure@strategycues.com -> StrategyCues Projects (Hobby) -> SingleHHOLeads
Your app will be live at https://single-hho-leads.vercel.app/

---
## 📎 Notes

* Ensure Supabase project is active and API keys are valid
* Do not expose sensitive keys in production (move to environment variables)
* Validate phone numbers before submission for better data quality

---

## 🛠️ Future Improvements

* Add input validation and error handling
* Integrate spam protection (e.g., CAPTCHA)
* Store Calendly booking status via webhook
* Add analytics tracking

---

## 📬 Contact

For any issues or improvements, please reach out to the project maintainer.

---
