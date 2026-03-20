# Student Progress Monitoring System

![Version](https://img.shields.io/badge/version-v1.1.0-blue.svg)
![Python](https://img.shields.io/badge/python-3.8%2B-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

A comprehensive, interactive system designed to process, analyze, and visualize student performance data. This tool streamlines the workflow from raw CSV assessment files to actionable insights, empowering educators to monitor progress, identify underperforming students, and generate personalized feedback.

---

## ✨ Features

* **Automated Data Preprocessing (ETL):** Cleans and normalizes raw CSV files from multiple formative and summative assessments. It automatically keeps the best attempts and scales grades to a standardized format before storing them in a centralized SQLite database.
* **Individual Performance Tracking:** Instantly retrieve and visualize a student's historical grades across all available assessments.
* **Per-Question Analysis:** Deep dive into specific assessments to compare a student's absolute score against the cohort average for every single question.
* **Underperformer Identification:** Automatically cross-reference formative participation and lowest grades against summative outcomes to flag students who may need early intervention.
* **🧠 AI Assistant (Structured RAG):** An integrated natural language interface powered by LLMs. Educators can query the database in plain English to uncover complex trends or generate comprehensive student reports. **These AI-generated reports dynamically include tailored advice for improving essential soft skills (e.g., communication, problem-solving, and time management) alongside technical programming feedback.**

---

## 📁 Project Structure

* `menu.ipynb`: The main entry point. A Jupyter Notebook providing a unified, widget-based graphical interface to run all system modules.
* `CWPreprocessing.py`: Handles the extraction, transformation, and loading (ETL) of raw CSV files into the database.
* `testResults.py`: Retrieves and plots overall performance trends for individual students.
* `studentPerformance.py`: Analyzes and visualizes student performance at the granular, per-question level.
* `underperformingStudent.py`: Identifies at-risk students based on specific attendance and grading criteria, plotting a comparative analysis.
* `ragAssistant.py` *(New)*: Connects the SQLite database to a Large Language Model using LangChain, enabling Text-to-SQL capabilities and intelligent feedback generation.
* `CWDatabase.db`: The SQLite database storing all processed assessment records.

---

## 🛠️ Requirements

Ensure you have Python 3.8+ installed along with the following packages:

```bash
pip install pandas matplotlib ipywidgets langchain langchain-community langchain-openai sqlalchemy

🚀 How to Use
1.Launch the Interface: Open and run all cells in menu.ipynb.

2.Load Modules: Click the "Load modules" button to initialize the system scripts.

3.Build Database: Navigate to the "CSV → SQLite" tab. Enter the path to your folder containing the raw CSV files and the desired database output path, then click "Convert CSVs → SQLite".

4.Analyze Data: Use the dedicated tabs to input a Student ID and generate visualizations for overall results, per-question breakdowns, or to identify the cohort's underperformers.

5.Interact with AI: Navigate to the "AI Assistant" tab to ask complex questions in plain English or request holistic performance summaries that include soft skill development strategies.
