# POTD-agent-self-on-the-go
An autonomous agent for self-POTD work..

# POTD-Agent-Self-On-The-Go 🚀

An autonomous workflow agent built with **n8n** that automatically propagates my **Problem of the Day (POTD)** solutions across multiple competitive programming accounts.

Instead of manually logging into multiple accounts and submitting the same solution every day, this agent detects when the POTD has been solved in a primary account and automatically replicates the submission across all other accounts.

---

## 🎯 Motivation

I maintain multiple accounts on coding platforms for tracking practice and experimentation:

* Multiple **LeetCode accounts**
* **LeetCode China accounts**
* Multiple **GeeksforGeeks (GFG) accounts**

Every day I solve the **Problem of the Day (POTD)** once in a designated primary account.
However, submitting the same solution to all other accounts requires:

1. Opening multiple browsers
2. Logging into each account
3. Navigating to the POTD page
4. Copy-pasting the solution
5. Submitting again

This process is repetitive and time-consuming.

**POTD-Agent-Self-On-The-Go** automates the entire workflow.

---

## ⚙️ Core Idea

1. Solve the **POTD** using a predefined primary account.
2. The agent detects that the problem has been solved.
3. The workflow automatically:

   * Retrieves the solution code
   * Logs into all configured accounts
   * Navigates to the POTD page
   * Pastes the solution
   * Submits the solution

Everything runs automatically with minimal manual intervention.

---

## 🧠 Features

* 🔄 **Automated Solution Replication**
  Submit the same POTD solution across multiple accounts.

* ⏱ **Event-Based Trigger**
  Workflow starts automatically once the POTD is solved in the primary account.

* 🔐 **Credential Handling**
  Supports multiple account credentials stored securely.

* 🤖 **Autonomous Workflow**
  Runs end-to-end using **n8n automation workflows**.

* 🔁 **Session Handling**
  If a login session expires, the agent attempts to log in again.

* 🧩 **Multi-platform Support**

  * LeetCode
  * LeetCode China
  * GeeksforGeeks

---

## 🏗 Architecture Overview

```
Primary Account (Solve POTD)
            │
            ▼
      Trigger Detection
            │
            ▼
        n8n Workflow
            │
   ┌────────┼─────────┐
   ▼        ▼         ▼
Login     Navigate    Submit
Accounts   POTD       Solution
   │
   ▼
All Accounts Updated
```

---

## 🛠 Tech Stack

**Automation Platform**

* n8n

**Backend Automation**

* Node.js scripts (optional helpers)

**Browser Automation**

* Playwright / Puppeteer

**Credential Storage**

* n8n credentials or environment variables

**Trigger Mechanism**

* Scheduled polling or webhook trigger

---

## 📂 Repository Structure

```
POTD-agent-self-on-the-go/ 
│
├── workflows/
│   └── potd-agent.json
│
├── scripts/
│   ├── login-handler.js
│   ├── submit-solution.js
│   └── session-checker.js
│
├── config/
│   └── accounts.json
│
├── docs/
│   └── architecture.md
│
└── README.md
```

---

## 🚦 Workflow Steps

1. **Trigger Detection**

   * Detect when POTD is solved in the primary account.

2. **Fetch Solution**

   * Retrieve solution code from the solved submission.

3. **Account Loop**

   * Iterate through configured accounts.

4. **Login Automation**

   * Log in if the session is expired.

5. **Navigate to POTD**

   * Open the problem page.

6. **Paste & Submit**

   * Insert solution and submit.

7. **Completion**

   * Confirm submission status.

---

## 🔐 Security Note

Credentials should **never be committed to the repository**.

Use:

* Environment variables
* n8n credential manager
* Secret managers

---

## 📌 Future Improvements

* AI agent for better login/session handling
* Telegram/Discord notifications
* Submission status tracking
* Automatic solution extraction from primary account
* Dashboard for monitoring submissions

---

## 👨‍💻 Author

**Tharun Tejas**

Built to automate repetitive coding platform workflows and experiment with autonomous agents using n8n.
