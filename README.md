# AI Task Genius Agent 🤖✅

> A learning project exploring LangChain ReAct agents through building an AI-powered task manager

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![LangChain](https://img.shields.io/badge/LangChain-latest-green.svg)
![Streamlit](https://img.shields.io/badge/Streamlit-1.45+-red.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## 🎯 Learning Objectives

This project was built to understand:
- How LangChain ReAct agents think and make decisions
- Implementing tool-based agents with custom functions
- Handling agent loops and error states
- Integrating LLMs (Gemini) with practical applications

## Features ✨

*   **Conversational Task Management:** Add, view, update, and delete tasks using natural language.
*   **Smart Task Cards:** Tasks are displayed in an intuitive card format with priority, category, and deadline badges, rendered from structured JSON data.
*   **AI-Powered Suggestions:** Get recommendations on what task to work on next based on priority, deadlines, and effort.
*   **Advanced Filtering & Search:** Quickly find tasks by keywords, category, importance, project, tags, or deadline.
*   **Time Tracking:** Log time spent on tasks.
*   **Productivity Analytics:** View statistics on completed tasks, overdue tasks, and average completion time.
*   **Duplicate Prevention:** The system intelligently checks for and warns about duplicate tasks.
*   **Customizable UI:** Rich custom CSS for an enhanced user experience, including animations and themes.
*   **Robust Agent Backend:** Utilizes a Langchain ReAct agent with custom tools, error handling, and loop prevention mechanisms.

## Tech Stack 🛠️

*   **Frontend:** Streamlit
*   **Backend AI Agent:**
    *   Langchain (Agents, Tools, Prompts)
    *   Google Gemini (via `langchain-google-genai`)
*   **Data Persistence:** JSON files (for tasks, analytics, templates)
*   **Date Parsing:** `dateparser`, `python-dateutil`
*   **Environment Management:** `python-dotenv`

## Project Structure 📂.
├── .gitignore
├── task_manager_app.py         # Streamlit frontend application
├── task_prioritizer_agent.py   # Langchain agent, tools, and task manager logic
├── tasks.json                  # Stores task data (example provided)
├── test_task_agent.py          # Test suite for the agent
├── .env.example                # Example environment file
├── requirements.txt            # Python dependencies
├── LICENSE                     # MIT License
└── README.md                   # This file

## Setup & Installation 🚀

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/YOUR_USERNAME/ai-task-genius-agent.git
    cd ai-task-genius-agent
    ```

2.  **Create and activate a virtual environment:**
    ```bash
    python -m venv venv
    # On Windows
    venv\Scripts\activate
    # On macOS/Linux
    source venv/bin/activate
    ```

3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Set up environment variables:**
    *   Rename `.env.example` to `.env`.
    *   Open `.env` and add your Google API Key:
        ```
        GOOGLE_API_KEY="YOUR_GOOGLE_AI_STUDIO_API_KEY"
        ```
    *   You can obtain a key from [Google AI Studio](https://aistudio.google.com/app/apikey).

## How to Run 🏃‍♂️

1.  **Run the Streamlit application:**
    ```bash
    streamlit run task_manager_app.py
    ```
    The application will open in your web browser.

2.  **Run the test suite (optional):**
    ```bash
    python test_task_agent.py
    ```

## Example Usage / Demo 🎬

**Example Commands:**
*   "Add task: Review project proposal by next Friday 📝"
*   "Show me all my tasks 📋"
*   "What should I work on next? 🤔"
*   "Track 30 minutes on task [ID] ⏱️"
*   "Delete task: Call John"
*   "Add tasks: 1. Design new logo by Wednesday. 2. Send client update by EOD. 3. Research competitors next week."

## Known Issues / Future Improvements 💡

### Current Limitations
*   **UI Rendering & Agent Output:** Task cards in Streamlit are rendered using structured JSON data returned by the agent's tools (e.g., `structured_tasks` from `show_tasks` or `search_tasks`). This ensures robust and accurate display. The agent's textual `Final Answer` is designed to be a brief, natural language summary, while the UI handles detailed task presentation. Future work could further refine the agent's textual output to minimize any descriptive overlap with the structured card data.
*   **Suggestion Chips Functionality:** The suggestion chips displayed below the chat input are currently visual only. Clicking them does not yet populate the input field; this JavaScript functionality needs to be fully implemented or debugged.
*   **Concurrency:** The JSON file-based data storage is not suitable for concurrent multi-user access. A database backend would be needed for such scenarios.
*   **Advanced Analytics:** More sophisticated analytics and visualizations could be added.
*   **Full CRUD for Templates:** Currently, templates are basic. Full management could be implemented.

### Planned Features 🚀
*   **🎤 Voice Commands:** Integrate speech-to-text capabilities to allow users to manage tasks hands-free. Planning to use Web Speech API or OpenAI Whisper for natural voice interactions.
*   **📅 Smart Calendar Integration:** 
    *   Sync with Google Calendar, Outlook, and other calendar services
    *   Automatically schedule tasks based on availability
    *   Conflict detection and smart rescheduling
    *   Time blocking for deep work sessions
*   **🔄 Real-time Sync:** Move from JSON to a proper database (PostgreSQL/MongoDB) with real-time synchronization
*   **📱 Mobile App:** Progressive Web App (PWA) support for mobile access
*   **🤝 Collaboration:** Multi-user support with task sharing and team features
*   **📊 Enhanced Analytics:** Machine learning-based insights on productivity patterns
*   **🔗 Integrations:** Slack, Discord, email notifications, and webhook support

## What I Learned 🧠

Building this project taught me:
- ReAct agents literally "reason" through problems step-by-step
- The importance of prompt engineering in agent behavior
- How to handle agent loops and error states gracefully
- The balance between natural language flexibility and structured data
- How to integrate LLMs into practical applications beyond simple chatbots

## Contributing 🤝

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/SaKinLord/ai-task-genius-agent/issues).

## License 📄

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments 🙏

- LangChain community for excellent documentation
- Google for Gemini API access
- Streamlit team for the amazing framework

---

**Note:** This is a learning project created to understand LangChain agents. While functional, it's primarily intended for educational purposes and as a starting point for more complex agent-based applications.
