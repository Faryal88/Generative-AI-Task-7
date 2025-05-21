# 🔍 Task 07 – Deep Dive into OpenAI Agents SDK

This repository explores the internal architecture and design principles behind the **OpenAI Agents SDK**. As part of the [Panaverse Learn Agentic AI](https://github.com/panaversity/learn-agentic-ai) series, this task focuses on understanding core abstractions like `Agent`, `Runner`, and the use of generics like `TContext`.


## 🚀 Objective

The main goal of Task 07 is to analyze how OpenAI's Agent framework is structured and to understand how agents are initialized, how prompts are handled, and how tool execution is managed behind the scenes.


## 🧠 Key Questions & Insights

### 1️⃣ Why is the `Agent` class defined as a `@dataclass`?

The `Agent` class is defined as a Python `@dataclass` to:

- Automatically generate boilerplate methods (`__init__`, `__repr__`, etc.)
- Clearly represent agents as structured, immutable configurations
- Improve readability, organization, and maintainability

🔗 [Agent Class Reference](https://openai.github.io/openai-agents-python/ref/agent/)


### 2️⃣ Why is the system prompt stored as `instructions`, and why can it also be a callable?

The `instructions` attribute:

- Can be either a **static string** or a **callable function**
- Allows for **dynamic prompt generation** based on runtime data (e.g., time of day, user profile)
- Provides flexibility to customize agent behavior programmatically


### 3️⃣ Why is the user prompt passed to `Runner.run()` and why is it a `@classmethod`?

- The user prompt is passed at runtime to make the agent interaction dynamic.
- `Runner.run()` is a `@classmethod`, enabling you to call it **without needing an instance**.
- This design supports **stateless execution**, which is ideal for task-based workflows and microservices.

🔗 [Runner Class Reference](https://openai.github.io/openai-agents-python/ref/run/)


### 4️⃣ What is the role of the `Runner` class?

The `Runner` class acts as the **execution engine** of the agent. Its responsibilities include:

- Managing the full agent lifecycle during interaction
- Orchestrating the processing of user prompts
- Handling tool calls and multi-step reasoning
- Returning the final output from the agent


### 5️⃣ What are Generics in Python and why is `TContext` used?

- **Generics** allow developers to write type-safe, reusable code.
- `TContext` is a **generic type placeholder** representing the shared state or memory across agent/tool calls.
- This enables the agent to maintain structured context without hardcoding the type, improving flexibility and extensibility.

## 📁 What You Will Do in This Task

- Analyze the source code and documentation of the `Agent` and `Runner` classes
- Understand the role of `TContext` and how context is maintained
- Optionally, build your own custom agent or tool to experiment with the SDK


## 📚 Resources

- [OpenAI Agents SDK Documentation](https://openai.github.io/openai-agents-python/)
- [Panaverse Agentic AI GitHub](https://github.com/panaversity/learn-agentic-ai)
- [Agents First Task Code](https://github.com/panaversity/learn-agentic-ai/tree/main/01_ai_agents_first)


## 👨‍💻 Author

**Alfred**  
Web Developer | AI Explorer  
[GitHub Profile](https://github.com/your-username)


## 🪪 License

This project is open-source and part of the [Panaverse](https://www.panaverse.co/) learning initiative. Feel free to use, modify, and share with proper attribution.

