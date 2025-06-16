# 🤖 MCP-Gemini Tool Agent

An AI-powered automation agent built with **Google Gemini**, **Model Context Protocol (MCP)**, and **Node.js**, capable of executing real-world tasks like posting to Twitter using natural language — all through structured tool calling and live communication via SSE.

⚙️ Designed for extensibility, real-time interactivity, and intelligent tool execution.

---

## 📌 Features

- 🧠 **AI-Powered Chat Agent** using Google Gemini 2.0
- 🛠️ **Structured Tool Invocation** via Model Context Protocol (MCP)
- 🔄 **Live Interaction** using Server-Sent Events (SSE)
- 📤 **Post to Twitter (X)** using natural language (e.g., "Post a tweet about clean energy")
- 🔧 Easily extensible with new tools (e.g., scheduling, notifications)
- 🧪 CLI-based interaction loop using Node.js

---

## 🧱 Tech Stack

| Layer         | Technology                     |
|--------------|---------------------------------|
| AI Engine     | Google Gemini (`@google/genai`) |
| Protocol      | Model Context Protocol (MCP)    |
| Server        | Node.js, Express.js             |
| Transport     | SSE (Server-Sent Events)        |
| Schema        | Zod (for tool validation)       |
| Client        | Node.js CLI (readline)          |

---

## 🖼️ Architecture Overview

┌────────────────────────────┐
│ User CLI Input │
└────────────┬───────────────┘
↓
┌────────────────────────────┐
│ Google Gemini Model │
│ (Function Calling Enabled) │
└────────────┬───────────────┘
↓
┌────────────────────────────┐
│ MCP Client ↔ Server │
│ (Tool List + Call Flow) │
└────────────┬───────────────┘
↓
┌────────────────────────────┐
│ Tool Handler: createPost │
│ (Posts to Twitter/X) │
└────────────────────────────┘

yaml
Copy
Edit

---

## ⚙️ How It Works

1. **User** types a command like:  
   _"Post a tweet about clean energy awareness."_

2. **Google Gemini** interprets the intent and generates a `functionCall` with `status` argument.

3. **MCP Server** validates input using `zod`, then executes `createPost` handler.

4. **Tool Result** is returned and appended to chat.
   


---

## 🧪 Sample Output

```bash
You: post a tweet about trees on twitter
AI: calling tool createPost
AI: Tool result: ✅ Tweet posted successfully.


Amlendu Pandey – Infinimus01
Full Stack Developer • AI Product Builder • Backend Enthusiast
📍 India | 🌐 Open to Remote Roles
