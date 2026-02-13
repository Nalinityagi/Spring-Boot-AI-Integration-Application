📌 AI Integration Spring Boot Application
📖 Overview

This project demonstrates how AI capabilities can be integrated into a Spring Boot backend application using OpenAI APIs.

The application exposes REST endpoints for:

Question & Answer service

Text Summarization

🏗 Architecture

The application follows layered architecture:

Controller → Service → AI Client → OpenAI API

Technologies used:

Java 21

Spring Boot 3+

WebClient

Jakarta Validation

Lombok

OpenAI API

🤖 AI Service Used

OpenAI Chat Completions API

Model:

gpt-4o-mini

🚀 Setup Instructions
 Clone Repository
git clone https://github.com/your-username/ai-spring-boot-app.git

 Set Environment Variable

Windows:

setx OPENAI_API_KEY "your-api-key"


Restart terminal after setting.

 Build Project
mvn clean install

 Run Application
mvn spring-boot:run


Application runs at:

http://localhost:8080

📡 API Endpoints
 Ask Question

POST /api/v1/ai/ask

Request:

{
  "question": "What is Java?"
}


Response:

{
  "answer": "Java is a programming language..."
}

 Summarize Text

POST /api/v1/ai/summarize

Request:

{
  "text": "Long paragraph here..."
}


Response:

{
  "summary": "Short summary here..."
}

❗ Exception Handling

The application uses a GlobalExceptionHandler to manage:

Validation errors

AI communication errors

Unexpected runtime exceptions
