<!DOCTYPE html>
<html>
<head>
<title>Chatbot API with Emotional State Detection</title>
</head>
<body>

<h1>Chatbot API with Emotional State Detection</h1>

<p>This project is a RESTful API built with FastAPI that features a chatbot using Retrieval-Augmented Generation (RAG) architecture and LangChain, enhanced by emotion detection.</p>

<h2>Features</h2>
<ul>
  <li><strong>Chatbot:</strong> The chatbot interacts with users through conversational prompts, generating responses based on user input and conversation history.</li>
  <li><strong>Emotion Detection:</strong> An emotion detector analyzes user input and classifies it into predefined emotional categories: <code>happy</code>, <code>sad</code>, <code>neutral</code>, <code>emotional</code>, or <code>confused</code>.</li>
  <li><strong>Session History:</strong> The chatbot maintains a session history, enabling context-aware conversations through a persistent SQLite database.</li>
</ul>

<h2>Getting Started</h2>

<h3>Prerequisites</h3>
<ul>
  <li>Python 3.8 or higher</li>
  <li>FastAPI</li>
  <li>LangChain</li>
  <li>SQLite</li>
  <li>Dotenv</li>
</ul>

<p>Install the dependencies by running:</p>

<pre><code>pip install fastapi pydantic langchain langchain_groq dotenv sqlite3</code></pre>

<h3>Setting Up the Project</h3>

<ol>
  <li>Clone the repository or download the project files.</li>
  <li>Create a <code>.env</code> file in the project root directory to store environment variables as needed.</li>
  <li>Run the API server by executing the following command:</li>
</ol>

<pre><code>uvicorn main:app --reload</code></pre>

<p>The server will start at <code>http://127.0.0.1:8000</code></p>

<h2>API Endpoints</h2>

<h3>Root Endpoint</h3>
<pre><code>GET /</code></pre>
<p>Returns a simple JSON response confirming that the server is running.</p>

<h4>Response Example</h4>
<pre><code>
{
  "Hello": "World"
}
</code></pre>

<h3>Chat Endpoint</h3>
<pre><code>POST /chat</code></pre>
<p>Accepts user input and returns the chatbot's response along with the detected emotional state.</p>

<h4>Request Body</h4>
<pre><code>
{
  "text": "User message here",
  "session_id": "unique_session_identifier"
}
</code></pre>

<h4>Response Example</h4>
<pre><code>
{
  "response": "Chatbot response here",
  "emotion": "detected_emotion"
}
</code></pre>

<h2>Detailed Code Overview</h2>

<h3>Project Structure</h3>
<ul>
  <li><code>main.py</code>: Contains the FastAPI application and endpoint logic.</li>
</ul>

<h3>Main Components</h3>

<ul>
  <li><strong>Session Management:</strong> Uses SQLChatMessageHistory to manage user conversation histories.</li>
  <li><strong>Chat Prompt Template:</strong> The <code>prompt</code> and <code>emotion_prompt</code> handle chatbot interactions and emotion detection, respectively.</li>
  <li><strong>CORS Middleware:</strong> Configured to allow cross-origin requests.</li>
</ul>

<h2>Contributing</h2>
<p>Contributions are welcome. Fork the repository, make your changes, and submit a pull request.</p>

<h2>License</h2>
<p>This project is licensed under the MIT License.</p>

</body>
</html>
