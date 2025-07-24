Here’s a polished, 🎨 visually appealing README for your project integration:

---

````markdown
# 🚀 MERN AI Resume Builder with Gemini Integration

**MERN** + **Google Gemini** = the ultimate AI-powered resume builder! 💼✨
**Frontend Code** -- https://github.com/Gautam-mali/ResumeXpert-frontend/
**Backend Code** -- https://github.com/Gautam-mali/ResumeXpert-Backend/
---

## 🧭 Table of Contents

1. [🔧 Features](#-features)  
2. [🛠 Tech Stack](#-tech-stack)  
3. [⚙️ Setup & Installation](#-setup--installation)  
4. [🌟 Gemini AI Integrations](#-gemini-ai-integrations)  
5. [📁 Endpoints & Usage](#-endpoints--usage)  
6. [🎨 Demo Screenshots](#-demo-screenshots)  
7. [🤝 Contributing](#-contributing)  
8. [📜 License](#-license)

---

## 🔧 Features

- ✅ **User Authentication** with JWT & bcrypt  
- 📄 **Full Resume CRUD**: create, edit, delete, real-time preview  
- 📊 **Progress Tracking**: percentage completion & dynamic bars  
- 🖼 **Image Upload**: secure photo uploads (JPG/PNG)  
- 🎨 **Theme & Template Selector**  
- 📥 **PDF Export** of resumes  
- 📱 **Fully Responsive UI** – mobile, tablet, desktop  
- 🤖 **Gemini-Powered**:

  - Auto-generate summaries & bullet points  
  - Tailor resumes to job descriptions  
  - Suggest and render design templates dynamically

---

## 🛠 Tech Stack

| Layer      | Technologies                     |
|------------|----------------------------------|
| **Frontend** | React, Tailwind CSS         |
| **Backend**  | Node.js, Express.js         |
| **Database** | MongoDB + Mongoose          |
| **Auth**     | JWT & bcrypt                |
| **AI**       | Google Gemini via GenAI SDK |

---

## ⚙️ Setup & Installation

1. **Clone Repo**  
   ```bash
   git clone https://github.com/your-username/mern-ai-resume-builder.git
   cd mern-ai-resume-builder
````

2. **Install Dependencies**

   ```bash
   cd server && npm install
   cd ../client && npm install
   ```

3. **Configure Env Variables**

   * Add `.env` files:

     **Server:**

     ```
     MONGO_URI=...
     JWT_SECRET=...
     GEMINI_API_KEY=...
     ```

     **Client (optional):**

     ```
     REACT_APP_API_URL=http://localhost:5000/api
     ```

4. **Start Servers**

   ```bash
   npm run dev   # runs both client & server
   ```

5. **Open in Browser**
   Visit `http://localhost:3000`

---

## 🌟 Gemini AI Integrations

Powered by **Google Gemini** via the GenAI SDK 🎯:

* **Content Generation**
  Submit job titles/descriptions for AI-crafted bullet points & summaries.

* **Resume Alignment**
  Enhance resumes based on job descriptions using prompt-engineered feedback.

* **Dynamic Templates**
  Ask Gemini for custom-themed templates like “minimalist with blue accents.”

> *Gemini 2.5 Flash model supports multimodal prompts and streaming generation* ([github.com][1], [github.com][2], [developers.google.com][3], [github.com][4], [github.com][5], [ai.google.dev][6])

---

## 📁 Endpoints & Usage

```http
POST /api/auth/register      # Register user
POST /api/auth/login         # Login + return JWT
GET  /api/resumes            # List user resumes
POST /api/resumes            # Create new resume
PUT  /api/resumes/:id        # Update
DELETE /api/resumes/:id      # Delete
POST /api/gemini/summary     # Generate AI summary
POST /api/gemini/template    # Generate template code
POST /api/gemini/align       # AI resume alignment feedback
```

Integration example (Node.js, server-side):

```js
import { GenerativeModel } from '@google/generative-ai';
const gemini = new GenerativeModel('gemini-2.5-flash', { apiKey: process.env.GEMINI_API_KEY });

const resp = await gemini.generateContent({
  temperature: 0.7,
  maxOutputTokens: 500,
  prompt: `Generate 3 professional bullet points for: ${jobTitle}`
});
```

---


## 🤝 Contributing

Contributions are welcome! 🎉

* 🐞 **Bug reports** & feature requests: open an issue
* 🛠 **Pull requests**: fork → branch → PR review

Please use clear commit messages and include tests where applicable.

---

## 📜 License

This project is licensed under the **MIT License**. Feel free to use, modify, and distribute! 😊

---

### ❤️ You’re all set!

Build and publish resumes faster, smarter, and with a little AI magic ✨

Enjoy, and reach out for help or ideas anytime!

[1]: https://github.com/google-gemini/cookbook/blob/main/README.md?utm_source=chatgpt.com "cookbook/README.md at main · google-gemini/cookbook · GitHub"
[2]: https://github.com/Yadhavaramanan/Digital-Resume-Builder-using-MERN-Stack/?utm_source=chatgpt.com "Digital Resume Builder (MERN Stack) - GitHub"
[3]: https://developers.google.com/learn/pathways/solution-ai-gemini-getting-started-web?utm_source=chatgpt.com "Getting started with the Gemini API and Web apps - Google Developers"
[4]: https://github.com/Aakashrawat08/resume-builder?utm_source=chatgpt.com "GitHub - Aakashrawat08/resume-builder: The Resume Builder App is a full ..."
[5]: https://github.com/danishshaikh04/ResumeBuilder-MERN/blob/main/README.md?utm_source=chatgpt.com "ResumeBuilder-MERN/README.md at main - GitHub"
[6]: https://ai.google.dev/gemini-api/docs/quickstart?utm_source=chatgpt.com "Gemini API quickstart - Google AI for Developers"
