# 📘 Deal Management Service - API Documentation

This guide explains how to set up, use, and update the API collection for the **Deal Management Service** using **Bruno**. We use Bruno to keep our API testing synced directly with our code repository.

## 1. Prerequisites

Before starting, ensure you have the following:

1.  **Project Code:** Clone the repository to your local machine.
    ```bash
    git clone https://github.com/mahendratechnosoft/Deal-Management-APICollection.git
    ```
2.  **Bruno Client:** Download and install the tool.
    * [Download Bruno](https://www.usebruno.com/downloads)

---

## 2. Importing the Collection

You can load the "Deal management service" collection in two ways.

### Option A: Open from Local Folder (Recommended)
*Best if you are a developer working on the backend code.*

1.  Open **Bruno**.
2.  Click **"Open Collection"**.
3.  Navigate to your project folder: `<Project_Path>/backend/api-collection` (or your specific path).
4.  Click **Open**.

### Option B: Clone Directly via Git
*Best if you only need the APIs and not the full backend code.*

1.  Open **Bruno**.
2.  Click **"Import Collection"** > **"Clone Git Repository"**.
3.  Enter the Project Repository URL.
4.  Select a location on your computer to save it.
5.  Click **Clone**.

---

## 3. Environment Setup (Critical)

To run APIs successfully, you must select the correct environment to load the variables.

1.  Look at the **top-right corner** of the Bruno window.
2.  Click the dropdown menu (it may currently say "No Environment").
3.  Select **`XpertBiz`**.

**Verifying Variables:**
Once `XpertBiz` is selected, the system will recognize:
* `{{baseUrl}}`: Points to your local server (e.g., `http://localhost:8080`).
* `{{bearerToken}}`: Automatically populated after you sign in.

---

## 4. How to Use & Authenticate

We have automated the authentication process. You do not need to manually copy/paste tokens.

### Step 1: Run Sign In
1.  In Bruno, expand the **Auth** folder.
2.  Select the **Sign In** request.
3.  Update the Body with valid credentials if necessary.
4.  Click **Run (->)**.

### Step 2: Auto-Token Script
* A script automatically runs after the response.
* It extracts the `jwtToken`.
* It updates the `{{bearerToken}}` variable inside the **XpertBiz** environment.

### Step 3: Run Any API
* Go to any other request (e.g., "Create Deal").
* Click **Run**.
* The request will automatically use the `{{bearerToken}}` generated in Step 2.

---

## 5. Fetching Latest Changes

Our API collection is version-controlled. When teammates add new APIs, follow these steps to see them:

**If you used Option A (Local Folder):**
Run this in your terminal:
```bash
git pull origin master
