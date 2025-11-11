# AI Agent Project Templates

This repository contains a set of templates to bootstrap a new software project with clear guidelines for AI-assisted development.

## How to Use

To start a new project using these templates, follow these steps:

1.  **Start a conversation with an AI assistant.**
2.  **Provide the assistant with the prompt from `PROMPT.md`**. This will configure the assistant to act as a "Project Scaffolding Assistant."
3.  **Answer the assistant's three simple questions**:
    *   Project Name
    *   Project Type (e.g., "web service", "CLI tool", "library")
    *   Primary Programming Languages
4.  The assistant will **immediately generate three customized documents** with sensible defaults:
    *   A project README (`PROJECT_README.md`)
    *   An AI agent instruction file (`AGENT.md`)
    *   A set of development rules for the agent (`RULES.md`)
5.  **Review and refine** the generated files to match your specific project needs.
6.  **Use these files** to bootstrap your new project repository.

## Core Components

*   **`PROMPT.md`**: A prompt to configure an AI assistant for quick, iterative project scaffolding. The assistant asks for minimal information and generates templates with sensible defaults.
*   **`templates/`**: This directory contains the base templates that will be populated by the assistant:
    *   `AGENT.md`: A template for providing instructions to an AI coding agent.
    *   `RULES.md`: A template for defining development standards and rules for an AI agent to follow.
    *   `PROJECT_README.md`: A comprehensive template for a project's `README.md` file.

## Philosophy

This scaffolding system is designed to **deliver value quickly** rather than requiring a lengthy interview process. The assistant generates working templates in seconds, and you can refine them iteratively as your project evolves. This approach reduces user fatigue and allows you to start coding faster.
