# Ollama REST API on Svelte

Simple testing of sending user input queries as prompt to official [Ollama Rest API](https://github.com/ollama/ollama/blob/main/docs/api.md) to get response from ollama api through Svelte as front-end framework here. Model used here is Llama3-8B. 

Better and complete version in progress..

## Prerequisites

- **Node.js**: Ensure you have Node.js installed.
- **Ollama**: Ollama is needed as localhosted LLM REST API. You can install it on [here](https://github.com/ollama/ollama)

## Installation

1. **Clone the repository:**

```
git clone https://github.com/0xrsydn/ollama-svelte.git
```

2. **Navigate to the project directory:**

```
cd ollama-svelte
```

3. **Install NPM packages:**

```
npm install
```

##Running The Project

1. **Start the Ollama server**

Before running the web-app, make sure to run the ollama server first. You can start the server using this command:

```
ollama serve
```

As we are using Llama3 model here, if you dont have Llama3-8B model, you can use this command (make sure your local machine can run it):

```
ollama run llama3
```

You can change the default model which is Llama3 in code if you want to.

2. **Start the Svelte development server**

```
npm run dev
```

This will start the development server and and you can view the application (in my case, its http://localhost:5173/).
