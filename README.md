📌 Spring Boot AI Integration Application
📖 Overview

This project demonstrates how Artificial Intelligence (AI) capabilities can be integrated into a Spring Boot backend application.

The application exposes REST APIs that provide AI-powered features such as:

✅ Question & Answer service

✅ Text Summarization

The application integrates with the OpenAI API to process user input and generate intelligent responses.

🏗 Architecture Overview

The application follows a clean layered architecture:

Controller → Service → AI Client → External AI API

Package Structure
com.example.aiapp
│
├── controller        # REST Controllers
├── service           # Business Logic Layer
├── client            # OpenAI API Integration
├── dto               # Request & Response DTOs
├── exception         # Custom Exceptions & Global Handler
└── AiAppApplication  # Main Application Class

Technologies Used

Java 17+

Spring Boot

Spring Web

WebClient

Jakarta Validation

Lombok

OpenAI API

🤖 AI Service Used

This application integrates with:

OpenAI Chat Completions API

Model used:

gpt-4o-mini


The AI service is called via Spring WebClient.

🚀 Setup Instructions
1️⃣ Clone the Repository
git clone https://github.com/Nalinityagi/Spring-Boot-AI-Integration-Application.git
cd Spring-Boot-AI-Integration-Application


Or download as ZIP and extract.

2️⃣ Set Environment Variable (Required)

You must configure your OpenAI API key.

On Windows (PowerShell):
setx OPENAI_API_KEY "your_openai_api_key_here"


Restart terminal after setting.

On Mac/Linux:
export OPENAI_API_KEY="your_openai_api_key_here"

3️⃣ Build the Project
mvn clean install

4️⃣ Run the Application
mvn spring-boot:run


Application runs at:

http://localhost:8080

📡 API Endpoints
🔹 1. Question & Answer API

Endpoint

POST /api/v1/ai/ask


Request Body

{
  "question": "What is Spring Boot?"
}


Response

{
  "answer": "Spring Boot is a Java-based framework that simplifies backend application development..."
}

🔹 2. Text Summarization API

Endpoint

POST /api/v1/ai/summarize


Request Body

{
  "text": "Spring Boot simplifies development by providing auto-configuration and embedded servers..."
}


Response

{
  "summary": "Spring Boot simplifies Java development through auto-configuration."
}

🛡 Validation & Exception Handling

The application uses:

@Valid for request validation

Custom AiServiceException

Global exception handler using @RestControllerAdvice

Handled scenarios:

Invalid input (400)

AI communication failure (500)

Unexpected runtime errors

🧪 Testing the APIs

You can test using:

Postman

Curl

Swagger (if added)

Example using curl:

curl -X POST http://localhost:8080/api/v1/ai/ask \
-H "Content-Type: application/json" \
-d '{"question":"What is Java?"}'

🔒 Security Note

The OpenAI API key is NOT stored in the repository.
It must be configured using environment variables.
