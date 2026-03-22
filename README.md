Feedback Service — Part B
Spring Boot Dashboard with Gemini AI Integration
This is Part B of a two-part final project for the Generative AI for Java and Spring Development course. It's a Spring Boot application that reads sentiment analysis results from Part A, enhances each feedback entry using the Google Gemini API, and displays everything in a dynamic web dashboard.
---
What It Does
Reads the structured output from Part A (`sentiment_feedback_output.txt`)
Sends each feedback comment to the Gemini AI API to:
Categorize the feedback (e.g. Customer Service, Product Quality, Store Experience)
Generate an actionable insight or recommendation
Exposes a REST API endpoint at `/getfeedback` returning enriched JSON
Displays a live dashboard with sentiment, category, and department distribution charts

---
Tech Stack
Java 21
Spring Boot 3.2.3
Thymeleaf — server-side HTML templating
Google Gemini API (`gemini-2.5-flash`) — AI categorization and insights
Chart.js — dashboard visualizations
Bootstrap 5 — responsive UI
Jackson — JSON processing
---

Steps
Clone the repository:
```bash
git clone https://github.com/ChiragPanjwani0304/feedback-service.git
cd feedback-service
```
Set your Gemini API key as an environment variable:
Windows (PowerShell):
```powershell
$env:GEMINI_API_KEY="your_api_key_here"
```
Mac/Linux:
```bash
export GEMINI_API_KEY=your_api_key_here
```
Place `sentiment_feedback_output.txt` (from Part A) in the project root.
Build and run:
```bash
mvn package
mvn spring-boot:run
```
Open your browser at:
```
http://localhost:8080
```
---

API Endpoints
Method	Endpoint	Description
GET	`/`	Dashboard UI
GET	`/getfeedback`	Returns all enhanced feedback as JSON
---
Environment Variables
Variable	Description
`GEMINI_API_KEY`	Your Google Gemini API key

The `application.properties` file uses `${GEMINI_API_KEY}` as a placeholder — your actual key is never stored in the codebase.
---
Dashboard Features
Sentiment Distribution — pie chart of Positive / Negative / Neutral
Category Distribution — bar chart of AI-assigned categories
Department Distribution — doughnut chart by store department
Recent Feedback Table — last 5 entries with sentiment badge, category, and AI insight
All Feedback Table — full list with refresh button
---
Part A
This project depends on the output of customer-service-platform which performs the initial sentiment analysis using Stanford CoreNLP.
---
Author
Chirag Panjwani
Final Project — Generative AI for Java and Spring Development

