# 💬 AI Chatbot using IBM Watson Assistant

This project is a  built using **IBM Watson Assistant** on IBM Cloud. The assistant is capable of understanding natural language and engaging in multi-turn conversations. This guide explains how to replicate or understand the setup of this chatbot.

---

## 📌 Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Step-by-Step Setup](#step-by-step-setup)
  - [1. Create IBM Cloud Account](#1-create-ibm-cloud-account)
  - [2. Set Up Watson Assistant Service](#2-set-up-watson-assistant-service)
  - [3. Create Assistant and Skill](#3-create-assistant-and-skill)
  - [4. Build the Dialog Flow](#4-build-the-dialog-flow)
  - [5. Test Your Assistant](#5-test-your-assistant)
  - [6. Deploy via Web Chat](#6-deploy-via-web-chat)
- [Preview](#preview)
- [Future Improvements](#future-improvements)
- [Credits](#credits)
- [License](#license)

---

## 🧠 Overview

This chatbot was created using **Watson Assistant** with no programming required. It handles common queries, offers dynamic responses, and can be easily embedded in websites or applications using IBM’s Web Chat feature.

---

## ✅ Prerequisites

- IBM Cloud Account → [Sign Up](https://cloud.ibm.com/registration)
- Internet browser
- Basic understanding of chatbot logic
- No coding or technical setup required

---

## 🛠️ Step-by-Step Setup

### 1. Create IBM Cloud Account

- Go to [https://cloud.ibm.com](https://cloud.ibm.com)
- Sign up for a free account (no credit card required)

---

### 2. Set Up Watson Assistant Service

- Go to the [Watson Assistant page](https://cloud.ibm.com/catalog/services/watson-assistant)
- Click **Create**
- Choose the **Lite Plan** (free tier)
- Wait for the service to be created in your IBM Cloud dashboard

---

### 3. Create Assistant and Skill

#### Assistant:
- Open Watson Assistant
- Click **Create Assistant**
- Name your assistant (e.g., “Virtual Support Bot”)

#### Skill:
- Inside the Assistant, click **Add dialog skill**
- Choose **Create skill**
- Select **Dialog skill**
- Name the skill (e.g., “Helpdesk Flow”) and click **Create**

---

### 4. Build the Dialog Flow

- Go to your skill’s **Intents** section and create intents like:
  - `#greet` → Hi, Hello, Good morning
  - `#help` → I need help, Can you assist me?
  - `#menu` → Menu For Breakfast,Lunch,Dinner?
  - `#faq_booking` → How can I book a slot?

- Then go to **Entities** (optional) if you want the bot to recognize names, products, etc.

- Go to **Dialog** and build conversation nodes using:
  - Conditions (e.g., `#greet`)
  - Responses (e.g., “Hello! How can I help you today?”)
  - Add **context** and **slots** for more advanced flows

---

### 5. Test Your Assistant

- Use the **Try it out** window in the top-right corner
- Type sample messages and verify the chatbot behaves correctly

---

### 6. Deploy via Web Chat

1. Go to your Assistant → **Integrations**
2. Click on **Web Chat**
3. Click **Add integration**
4. Customize the appearance and copy the generated **embed code**
5. Paste the script into the `<body>` of your website's `index.html`

Example:
```html
<script>
  window.watsonAssistantChatOptions = {
      integrationID: "your-integration-id",
      region: "your-region", 
      serviceInstanceID: "your-service-id",
      onLoad: function(instance) { instance.render(); }
  };
  setTimeout(function(){
    const t = document.createElement('script');
    t.src = "https://web-chat.global.assistant.watson.appdomain.cloud/loadWatsonAssistantChat.js";
    document.head.appendChild(t);
  });
</script>
