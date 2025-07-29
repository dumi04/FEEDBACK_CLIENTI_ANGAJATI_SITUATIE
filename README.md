🗣️ Feedback Collection, Sentiment Analysis & Google Sheets Logging – n8n Workflow
This project leverages n8n, Google Sheets, and OpenAI (via LangChain) to automate feedback collection, sentiment classification, email acknowledgment, and weekly reporting for both clients and employees.

🔄 Key Features
🌟 For Client Feedback
Collects feedback via a web form

Classifies sentiment based on rating

Logs data to Google Sheets

Generates personalized AI email responses

Automatically sends thank-you or follow-up emails depending on sentiment

🧑‍💼 For Employee Feedback
Collects anonymous weekly feedback on office atmosphere

Analyzes mood via OpenAI (e.g. tensioned, positive)

Logs data to a dedicated sheet

Scheduled Friday feedback report email to HR or management

📊 Operator Performance Reporting
Scheduled monthly script calculates average scores per operator

Alerts when any operator falls below threshold

Updates a dedicated Google Sheet with score averages

🧰 Workflow Modules
📝 Client Feedback Workflow
Form Trigger: Captures responses (Name, Operator, Rating, Mentions, Contact)

Sentiment Classification: Uses LLM to reduce feedback rating to a sentiment word

Merge & Append: Stores feedback and sentiment into Google Sheets

Auto-Email: AI writes and sends a customized thank-you/follow-up message

🔁 Monthly Operator Stats
Scheduled Trigger: Runs monthly

Sheet Reader + Code Node: Aggregates scores per operator

Conditional Email Alert: Sends Gmail alert if score < 3

Sheet Update: Logs average score and count

🧘 Employee Mood Feedback
Weekly Form: Captures mood rating and suggestions

LLM Analysis: Extracts mood classification from feedback

Google Sheet Append: Logs to FEEDBACK ANGAJATI tab

Friday Scheduled Trigger: Sends mood summary to office inbox

🧾 Google Sheet Tabs Overview
Sheet Name	Purpose
Feedback Clients	Client responses + sentiment
MEDIE NOTE	Monthly average ratings per operator
FEEDBACK ANGAJATI	Weekly anonymous staff feedback

🧪 Form Field Example (Client)
Nume (required)

Operator (dropdown)

Care este nota... (dropdown 1-5)

Alte mentiuni (optional)

Contact (email, required)

🧪 Form Field Example (Employee)
Nume

Cum a fost atmosfera... (dropdown 1-5)

Propuneri (textarea)

🧠 AI Prompts Used
Sentiment Reduction:

"Clasifica sentimentul din formularul acesta de feedback {{ nota }} si trimite mi un singur cuvant descriptiv"

Client Email Response:

Writes a thank-you or follow-up email based on sentiment and name

Employee Mood Summary:

"Clasifica starea de spirit pe baza acestor 2 {{ atmosfera }}, {{ propuneri }} si trimite mi doar o fraza scurta"

📬 Example Auto Emails
✅ Positive Feedback
Mulțumim că ți-ai făcut timp să ne lași feedback, {{ Nume }}!
Apreciem sincer sprijinul tău.

– Company-Name

❌ Negative Feedback
Îți mulțumim, {{ Nume }}, pentru că ne-ai împărtășit părerea ta.
Ne pasă de experiența ta – cum ne putem îmbunătăți?

– Company-Name
