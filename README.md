# 📬 Automatic Email Delivery System using n8n (LLM Powered)

This project automates personalized email delivery by integrating **Google Sheets**, **OpenAI**, and **Gmail** via **n8n workflow automation**. The system generates and sends customized, personality-driven follow-up emails.

## 🔧 Features

* ✍️ **LLM-Based Email Generation**
  Uses OpenAI (e.g., `gpt-3.5-turbo`) to craft short, professional email messages based on user personality traits.

* 📑 **Google Sheets Integration**
  Reads recipient details (Name, Email, Personality) from a Google Sheet.

* 📤 **Automated Gmail Sending**
  Sends the generated emails to each recipient through Gmail API.

* 🔗 **Dynamic Workflow Execution**
  Full automation using n8n with nodes for:

  * Trigger
  * Google Sheets (Get Rows)
  * OpenAI (LLM Chain)
  * Gmail (Send Message)


## 🖼️ Sample Input Sheet (Google Sheets)

| Mail id                                                   | Name  | Character                                                         |
| --------------------------------------------------------- | ----- | ----------------------------------------------------------------- |
| [gokulkannankh@gmail.com](mailto:gokulkannankh@gmail.com) | Gokul | Ambitious – Tailor messages around growth, leadership, and goals. |

---

## 🧠 Prompt Structure (LLM Node)

```
To name: {{ $json.Name }}
Personality: {{ $json.Character }}
```

**System Prompt**

> Generate a professional yet friendly email body without subject. The tone and style of the email should reflect the personality type. The content should be on "Follow-Up on Our Recent Discussion". Create a short mail content with 90–100 words. The mail is addressed to "To name". Sign the mail as Forgemind AI.

---

## 📨 Sample Output

```text
Hello Gokul,

I hope this message finds you well. I wanted to follow up on our recent discussion regarding your career goals and aspirations. Your ambition and drive towards growth and leadership are truly inspiring. I believe that setting clear goals is key to achieving success, and I am here to support you every step of the way. If you have any further thoughts or updates to share, feel free to reach out. Looking forward to seeing your progress towards your objectives.

Best regards,  
Forgemind AI
```

---

## 🔄 Workflow Overview

1. **Trigger:** Manual execution
2. **Google Sheet Node:** Fetch user info (email, name, personality)
3. **LLM Chain (OpenAI):** Generate email content
4. **Gmail Node:** Send message using dynamic recipient & message

![n8n workflow](n8n%20workflow.png)

<img width="1920" height="1080" alt="Sheet data" src="https://github.com/user-attachments/assets/88793dec-a6c4-4110-9621-7981b3972407" />


<img width="1920" height="1080" alt="Openai Model" src="https://github.com/user-attachments/assets/9ef5debd-cd2f-48a2-b5d7-4909a20c43f0" />


<img width="1920" height="1080" alt="Basic LLM chain" src="https://github.com/user-attachments/assets/b18bc6e9-0dc5-431e-b7d7-91846264505a" />


<img width="1920" height="1080" alt="Gmail" src="https://github.com/user-attachments/assets/0e80d0e9-1d48-4fc3-b29c-0cebf88bf568" />


<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1e7c6a61-be97-450f-83d0-919f41b1f0e1" />


<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f6d4cac8-e6f1-489e-8950-b5672d1a634a" />


<img width="1920" height="1080" alt="Output" src="https://github.com/user-attachments/assets/c909781c-54dd-40aa-bf37-f46f0eb4d635" />

---

## 🧪 Requirements

* n8n installed locally or hosted
* Google account connected for Sheets & Gmail
* OpenAI API credentials

---

## 🚀 How to Use

1. Clone the repo and import the workflow JSON into n8n.
2. Set up your credentials for:

   * Google Sheets
   * Gmail
   * OpenAI (GPT model)
3. Add your data to Google Sheets.
4. Click **Execute workflow** or schedule it via trigger.

---

## 📂 File Structure (for reference)

```
📁 automation-mail-n8n/
├── workflow.json
├── README.md
```

---

## 🧑‍💻 Author

**Gokulkannan K H** – Developer, Nithra Apps India Pvt Ltd

---

Let me know if you want a downloadable `.md` file or help exporting your `workflow.json` for sharing.
