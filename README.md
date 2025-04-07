# QuizGenie

![Banner](/assets/banner.jpg)

## Overview

QuizBot is an AI-powered quiz platform designed to help students and learners strengthen their understanding of various subjects. By using advanced AI technology, QuizBot creates quizzes based on the documents users upload (such as textbooks, notes, or scholarly papers). It offers instant feedback and detailed explanations, making learning both effective and engaging.

## Objective:

Many students struggle to find accessible and efficient ways to review and retain information. QuizBot was created to address this challenge by providing instant feedback and interactive quizzes based on any document you upload. With this tool, learners can reinforce their knowledge at their own pace, get detailed explanations for each question, and truly understand the material they’re studying. The goal is to create a fun and dynamic learning experience that helps users excel academically.

## Features:

- **AI-Generated Quizzes:** Automatically generate quizzes based on your uploaded documents (e.g., textbooks, research papers).

- **Instant Feedback:** Get immediate feedback on your answers, helping you quickly spot strengths and areas to improve.

- **Detailed Explanations:** After each question, you'll receive a thorough explanation to help you understand why the answer is correct (or incorrect).

- **Custom Learning Experience:** The quizzes are tailored specifically to the content of your uploaded documents, so you’re always studying exactly what you need.

## Technologies Used

- **Python**: Powers the backend logic behind QuizBot.

- **Langchain**: Handles the natural language processing to understand and process text effectively.

- **ChromaDB**: Manages the data, ensuring quick and efficient access to your documents and quiz content.

- **Google Gemini**: Drives the AI content generation, helping create quizzes from your documents.

- **Streamlit**: Provides a simple, user-friendly interface to make the quiz experience easy to use and accessible.

## Implementation

### Agentic Workflow (RAG)
![Task 9 Overview](/assets/implementation.png)

*RAG implementation Architecture*

### Snapshots

**1. PDF Input**

![Generate Quiz Algorithm Input](/assets/pdf_input.png)


**2. Generated Questions**

![Screen State Handling](/assets/generated_question.png)

## Setup Steps
Here’s a quick guide to get everything up and running, from setting up your Google Cloud account to installing the necessary packages.

### 1. Create a Google Cloud Account

1. **Visit Google Cloud**: Go to the [Google Cloud website](https://cloud.google.com/).
2. **Sign Up/In**: Click on the "Get started for free" button and follow the instructions to sign up or sign in with your Google account.
3. **Free Trial**: If you're new to Google Cloud, you will receive a free trial with $300 in credits.

### 2. Create a Google Cloud Project

1. **Go to the Google Cloud Console**: Navigate to the [Google Cloud Console](https://console.cloud.google.com/).
2. **Create a New Project**:
   - Click on the project drop-down menu at the top of the page.
   - Click "New Project".
   - Enter your project name, select a billing account, and choose a location.
   - Click "Create".

### 3. Enable Required APIs

1. **Navigate to APIs & Services**:
   - In the left-hand menu, go to "APIs & Services" > "Library".
2. **Enable APIs**:
   - Search for and enable the following APIs:
     - AI Platform API
     - Google Gemini API (if applicable)
     - Any other related APIs your project might need (e.g., Cloud Storage, Compute Engine).

### 4. Create a Service Account and Key

1. **Navigate to IAM & Admin**:
   - In the left-hand menu, go to "IAM & Admin" > "Service accounts".
2. **Create a Service Account**:
   - Click "Create Service Account".
   - Enter a name and description for the service account.
   - Click "Create and continue".
3. **Grant Permissions**:
   - In the "Grant this service account access to project" section, add the necessary roles:
     - AI Platform Admin
     - Google Gemini User
     - Other roles as needed (e.g., Storage Admin for Cloud Storage).
   - Click "Continue".
4. **Create a Key**:
   - Click "Done" to finish creating the service account.
   - In the service account list, find the newly created service account and click on it.
   - Go to the "Keys" tab.
   - Click "Add Key" > "Create new key".
   - Select "JSON" and click "Create".
   - Download the JSON key file. This is your service account key.

### 5. Set Up Your Project Directory

1. **Create a /secrets Directory**:
   - In the root folder of this repository, create a directory named `secrets`.

2. **Place the Service Account Key File**:
   - Move the downloaded JSON key file to the `secrets` directory.

### 6. Create `.env` file
- We will make use of this file to store environment variables for the projects.
- In the `/app` directory we will create and `.env` file.
    ```
    GCLOUD_SERVICE_ACCOUNT_KEY_PATH=<service-account-json-file-name>
    PROJECT_ID=<your-gcp-project-id>
    PROJECT_LOCATION=<your-gcp-project-location>
    ```

Sure, here is the final step to create a Conda environment using the `env.yml` file inside your repository:

### 7. Create a Conda Environment Using `env.yml`

1. **Ensure Miniconda/Anaconda is Installed**:
   - Make sure you have Miniconda or Anaconda installed on your system. You can download and install it from the [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/distribution) websites.

2. **Navigate to Your Project Directory**:
   - Open a terminal or PowerShell window and navigate to the root of your project directory where the `env.yml` file is located.

   ```sh
   cd /QuizBot
   ```

3. **Create the Conda Environment**:
   - Use the `conda env create` command to create the environment from the `env.yml` file.

   ```sh
   conda env create -f env.yml
   ```

4. **Activate the Conda Environment**:
   - After the environment is created, activate it using the `conda activate` command followed by the name of the environment (which is defined in the `env.yml` file).

   ```sh
   conda activate quizbot
   ```

By following these steps, you will have a fully configured project environment, ready to interact with Google Cloud services and use the necessary Python packages specified in your `env.yml` file.

