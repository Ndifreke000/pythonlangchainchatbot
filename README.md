# README

## Overview

This repository contains a project that leverages the LangChain framework and OpenAI's GPT-4 model to create an automated assistant named LearnPal. LearnPal is designed to help students check their grades for nine courses in a conversational and friendly manner. The assistant can load a PDF document, extract its content, and use this information to assist with student interactions.

## Features

- **Dialogue Memory:** Keeps track of the conversation context to provide coherent and relevant responses.
- **Dialogue Logging:** Logs all conversations to a text file for later analysis.
- **Document Access:** Allows the assistant to access and utilize the content of a PDF document for context augmentation.
- **Interactive Grading:** Students can check their grades and scores for specific courses through a conversational interface.

## Setup Instructions

### Prerequisites

Ensure you have the following packages installed:

- `python-dotenv`
- `openai`
- `langchain`
- `pdfplumber`

You can install them using pip:

```bash
pip install python-dotenv openai langchain pdfplumber
```

### Environment Variables

Create a `.env` file in the root directory of your project and add your OpenAI API key:

```bash
OPENAI_API_KEY=your_openai_api_key_here
```

### Running the Script

1. **Upload PDF Document:**

   The script includes a step to upload a PDF document. Ensure you have a PDF document ready to upload when prompted.

2. **Load PDF Content:**

   The script extracts text from the uploaded PDF using the `pdfplumber` library. This content is used by the assistant for context augmentation.

3. **Start the Conversation:**

   The script enters a loop where it waits for user input and responds accordingly. The conversation is logged in a text file named with the current date and time.

## Usage

- **Greet and Verify:** LearnPal first greets the student and asks for their name and serial number. The serial number acts as a password and must be in the format of DD/MM/YY. If the serial number format is incorrect, LearnPal responds with "Incorrect serial number/password."
  
- **Provide Grades:** Once verified, LearnPal asks for the student's scores and determines their grades based on a predefined grading scale. The grading scale is as follows:
  - 70 or higher: A
  - 60-69: B
  - 50-59: C
  - 45-49: D
  - 40-44: E
  - Below 40: Fail

- **Course Queries:** Students can ask for their grades and scores for specific courses by requesting information such as "Show me course A" or "What's my grade in course B?"

- **Sign Out:** If a student wants to sign out and let another person sign in, they can simply say "Sign out." LearnPal will then prompt the next person to sign in.

### Note

The dialogue and interactions are subject to change as the assistant is designed to generate responses based on random scores for different courses.
