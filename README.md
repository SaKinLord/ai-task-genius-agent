# AI Task Genius Agent 🤖✅

A sophisticated task management assistant powered by Streamlit and a Langchain ReAct agent using Google's Gemini model. Manage your tasks through a conversational interface, get smart suggestions, and track your productivity.

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

## Project Structure 📂

.
├── .gitignore
├── task_manager_app.py # Streamlit frontend application
├── task_prioritizer_agent.py # Langchain agent, tools, and task manager logic
├── tasks.json # Stores task data (example provided)
├── test_task_agent.py # Test suite for the agent
├── .env.example # Example environment file
├── requirements.txt # Python dependencies
└── README.md # This file


## Setup & Installation 🚀

1.  **Clone the repository:**
    ```bash
    git clone <my-repo-url>
    cd <my-repo-name>
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

*(Consider adding a GIF or a link to a short video walkthrough here)*

**Example Commands:**
*   "Add task: Review project proposal by next Friday 📝"
*   "Show me all my tasks 📋"
*   "What should I work on next? 🤔"
*   "Track 30 minutes on task [ID] ⏱️"
*   "Delete task: Call John"
*   "Add tasks: 1. Design new logo by Wednesday. 2. Send client update by EOD. 3. Research competitors next week."

## Known Issues / Future Improvements 💡

*   **UI Rendering & Agent Output:** Task cards in Streamlit are rendered using structured JSON data returned by the agent's tools (e.g., `structured_tasks` from `show_tasks` or `search_tasks`). This ensures robust and accurate display. The agent's textual `Final Answer` is designed to be a brief, natural language summary, while the UI handles detailed task presentation. Future work could further refine the agent's textual output to minimize any descriptive overlap with the structured card data.
*   **Suggestion Chips Functionality:** The suggestion chips displayed below the chat input are currently visual only. Clicking them does not yet populate the input field; this JavaScript functionality needs to be fully implemented or debugged.
*   **Concurrency:** The JSON file-based data storage is not suitable for concurrent multi-user access. A database backend would be needed for such scenarios.
*   **Advanced Analytics:** More sophisticated analytics and visualizations could be added.
*   **Full CRUD for Templates:** Currently, templates are basic. Full management could be implemented.

## Contributing 🤝

Contributions, issues, and feature requests are welcome!

## License 📄

*(Choose a license, e.g., MIT License, or state "This project is for demonstration purposes.")*