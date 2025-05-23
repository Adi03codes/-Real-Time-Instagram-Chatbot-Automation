# Real-Time-Instagram-Chatbot-Automation
Automated Instagram chatbot with customizable reply logic, perfect for high-volume influencer pages.


## Tech Stack
| Layer        | Technology                         |
|--------------|-------------------------------------|
| Frontend     | Next.js, TypeScript, Tailwind CSS  |
| Backend      | Node.js, MongoDB, AWS Lambda       |
| Auth         | OAuth2 (Instagram API)             |
| Deployment   | Vercel (Frontend), AWS EC2 & Lambda |

## Features
- 💬 Real-time chatbot responses
- 🔁 Customizable message templates
- 📈 Usage statistics and analytics
- ☁️ Serverless Lambda processing for scalability

## UI Pages
- **Bot Setup Wizard**
- **Chatbot Logic Designer (Drag & Drop)**
- **Campaign Performance Dashboard**

## Folder Structure
```
/instagram-chatbot
├── /frontend
│   ├── /pages
│   ├── /components
├── /backend
│   ├── /lambda
│   ├── /handlers
├── /shared
└── README.md
```

## AWS Lambda Function (Chatbot Handler)
```js
// backend/lambda/chatbotHandler.js
const AWS = require('aws-sdk');
const db = require('../handlers/db');

exports.handler = async (event) => {
  const message = JSON.parse(event.body);
  const reply = await db.getAutoReply(message.text);
  return {
    statusCode: 200,
    body: JSON.stringify({ reply }),
  };
};
```
