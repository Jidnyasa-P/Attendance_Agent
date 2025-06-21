# 📊 Attendance Analyzer Agent

An AI-powered autonomous agent that analyzes daily attendance data from Google Sheets, determines who is **Present**, **Late**, or **Absent**, and writes the summary back to a report sheet—completely hands-free.

Built using **n8n**, **Google Sheets**, and **Azure OpenAI GPT-4o**.

---

## 🚀 Features

* 🕒 **Runs Daily at 10:01 AM** via schedule trigger
* 📄 **Reads Time-In Data** from Google Sheets
* 🤖 **Uses GPT-4o** to classify each entry
* 📊 **Writes Summary** back to a new Google Sheet or logs it
* 🔁 **Fully Automated Workflow**—no human input needed

---
## 🧠 🛠 Workflow Diagram
![Screenshot 2025-06-21 214657](https://github.com/user-attachments/assets/cb889dba-6007-4cdd-bf96-71ec6e09416c)

## 🧠 AI Classification Logic

| Status  | Rule                                  |
| ------- | ------------------------------------- |
| Present | Time-In before 09:10 AM               |
| Late    | Time-In between 09:10 AM and 10:00 AM |
| Absent  | Time-In after 10:00 AM or empty       |

---

## 🛠 Tech Stack

* [n8n](https://n8n.io/) – Workflow Automation
* [Google Sheets API](https://developers.google.com/sheets/api)
* [Azure OpenAI (GPT-4o)](https://azure.microsoft.com/en-us/products/ai-services/openai-service)

---

## 📂 Workflow Structure

```
Schedule Trigger (10:01 AM daily)
   ↓
Google Sheets (Get Rows)
   ↓
Code Node (Format attendance prompt)
   ↓
AI Agent (GPT-4o – classification)
   ↓
Code Node (Extract and clean JSON output)
   ↓
Google Sheets (Append summary row)
```

---

## 🖼 Sample Output

```
"{
  Present: Jidnyasa Patil, Tanish Goyal,
  Late: Aarav Gupta,
  Absent: Sanya Mehta, Riya Shah
}"
```

---

## 📈 Future Scope

* Email/Slack daily reports
* Visual dashboards
* Pattern tracking (absentee trends)
* Face recognition integration

---

## 🙌 Credits

Made with ❤️ for the **AI Agent Mini Hackathon** hosted by K.A.M.A.L.A

**Author:** Jidnyasa Patil
