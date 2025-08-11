**Agent Name**: Pristine

**Description**:
Pristine is an autonomous AI agent designed for intelligent repository management and issue handling on GitHub. It continuously monitors a specified GitHub repository for new events, leverages Large Language Models (LLMs) to analyze the context and make decisions, and then executes a series of defined actions to manage issues, documentation, and tests. It also provides a real-time web-based monitoring dashboard for transparency into its operations.

**Key Features**:
*   **Autonomous Issue Management**: Monitors GitHub for new commits, issues, and comments, and intelligently decides on actions such as creating, updating, or closing issues.
*   **LLM-Powered Decision Making**: Integrates with Large Language Models (e.g., OpenAI) to process repository context, generate "thoughts," and determine a sequence of actions to perform.
*   **Comprehensive GitHub Interaction**: Capable of cloning and pulling repositories, creating, retrieving, and closing issues, adding or removing labels, and commenting on or editing issue details.
*   **Contextual Memory**: Stores and retrieves information in its internal memory to maintain continuity and inform future decisions.
*   **Real-time Monitoring Dashboard**: Provides a local web interface (HTTP) to visualize a history of all agent actions and LLM interactions, aiding in debugging and understanding agent behavior.
*   **Flexible Configuration**: Configured entirely through environment variables, allowing for easy deployment and customization.

**Inputs**:
*   **Environment Variables**:
    *   `GITHUB_PERSONAL_ACCESS_TOKEN`: Your GitHub Personal Access Token for API authentication.
    *   `GITHUB_REPOSITORY_OWNER`: The owner (user or organization) of the target GitHub repository.
    *   `GITHUB_REPOSITORY_NAME`: The name of the target GitHub repository.
    *   `GITHUB_REPOSITORY_ISSUES_BRANCH`: (Optional) The name of the branch where issues will be managed. Defaults to `issues`.
    *   `OPENAI_API_KEY`: Your OpenAI API key for LLM integration.
    *   `OPENAI_API_BASE`: (Optional) The base URL for the OpenAI API. Defaults to `https://api.openai.com`.
    *   `OPENAI_API_MODEL`: (Optional) The name of the OpenAI model to use. Defaults to `gpt-3.5-turbo`.
*   **GitHub Events (via GitHub API polling)**: New commits, newly created issues, updates to existing issues (e.g., comments, label changes, state changes).

**Outputs**:
*   **GitHub API**:
    *   Creation, updates, and closure of GitHub issues.
    *   Comments on issues.
    *   Addition or removal of labels on issues.
*   **HTTP (Web Dashboard)**:
    *   A web interface accessible on port 5005, displaying real-time logs of agent actions and LLM call history.
*   **Stdout/Console**: Operational logs and status messages during execution.