# CRM API Documentation

This guide explains how to set up and use the API collection for the CRM Deal Management project using **Bruno**.

## 1. Initial Setup

1.  **Install Bruno:** Download from [usebruno.com](https://www.usebruno.com/).
2.  **Open Collection:**
    * Launch Bruno.
    * Click **Open Collection**.
    * Navigate to the project folder and select the `api-collection` folder (inside `backend/`).
3.  **Select Environment:**
    * In the top-right corner, click the dropdown menu.
    * Select **`deal management`**.
    * *Note: This sets the `{{baseUrl}}` to your local server.*

## 2. Authentication (Important)

We use **JWT Authentication** with an automated script. You do not need to manually copy tokens.

### How to Log In:
1.  Expand the **`Auth`** folder in the sidebar.
2.  Select the **`Sign In`** request.
3.  Update the **Body** with your credentials (if needed).
4.  Click **Run (->)**.

**What happens automatically?**
* The script captures the `jwtToken` from the response.
* It automatically sets the `{{bearerToken}}` variable in your current session.
* It sets your user role (Admin/Employee).

## 3. Using the API

Once you have run the **Sign In** request successfully, you can use any other API endpoint immediately.

* **Authorization:** All protected endpoints use `{{bearerToken}}` automatically.
* **Variables:**
    * `{{baseUrl}}`: Points to the backend server (e.g., `http://localhost:8080`).
    * `{{bearerToken}}`: The current session's access token.

## 4. Workflow for Updates

Our API collection is version-controlled via Git.

* **To get updates:** Always run `git pull` before testing. This ensures you have the latest API definitions from the team.
* **To share changes:** If you add a new API request, simply save it (Ctrl+S) and commit the `.bru` file to Git.
