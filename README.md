# Google Forms Creation & Review System

This project allows users to dynamically create Google Forms from a text-based question list, review them, and send them via email upon approval.

## Features

*   **FastAPI Backend:**
    *   Accepts text input for survey questions.
    *   Integrates with Google Forms API to create forms.
    *   Implements a review workflow (Draft -> Approved).
    *   Sends email notifications via Gmail API upon approval.
    *   Stores survey metadata in an SQLite database.
    *   Exposes an OpenAPI specification (`/docs`, `/openapi.json`).
*   **ReactJS Frontend:**
    *   Allows manual entry of survey questions.
    *   Displays newly created forms for review.
    *   Allows approval of forms, triggering email notifications.
    *   Supports deleting surveys (soft delete).
*   **Python SDK:**
    *   Generated via OpenAPI Generator CLI for programmatic API interaction.
*   **Automation Scripts:**
    *   Scripts for easy setup and execution of the system.

## Prerequisites

*   Python 3.8+ and pip
*   Node.js and npm
*   Google Cloud Platform Account
*   `openapi-generator-cli` (Install with `npm install @openapitools/openapi-generator-cli -g`)

## Google Cloud Setup

1.  Go to the [Google Cloud Console](https://console.cloud.google.com/).
2.  Create a new project (or select an existing one).
3.  Enable the **Google Forms API** and **Gmail API** for your project.
    *   Search for "Google Forms API" in the API Library and enable it.
    *   Search for "Gmail API" in the API Library and enable it.
4.  Create OAuth 2.0 Credentials:
    *   Navigate to "APIs & Services" -> "Credentials".
    *   Click "Create Credentials" -> "OAuth client ID".
    *   Select Application type: "Desktop app" (or "Web application" for more advanced setups).
    *   Give it a name (e.g., "Forms App Client").
    *   Click "Create".
    *   Download the JSON file. Rename it to `credentials.json`.
5.  **Place the `credentials.json` file into the `backend/` directory of this project.**

## Project Structure