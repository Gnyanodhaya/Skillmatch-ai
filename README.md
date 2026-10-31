# 🎯 SkillMatch AI — Resume & Job Match Analyzer

[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white)](https://streamlit.io)
[![NLP](https://img.shields.io/badge/NLP-TF--IDF-green)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**🔗 Live Demo:** [Insert your deployed Streamlit Cloud link here]

## 📌 Overview
**SkillMatch AI** is an intelligent, locally-processed Natural Language Processing (NLP) tool designed to help students, graduates, and job seekers align their resumes with specific job descriptions. It identifies exact skill gaps, calculates a contextual match score, and provides actionable recommendations.

## ⚠️ The Problem
Students often struggle to manually identify which keywords and technical skills their resume is missing when applying for jobs. Submitting a non-tailored resume usually leads to instant rejection by Applicant Tracking Systems (ATS).

## 💡 The Solution
SkillMatch AI automates the comparison. Instead of relying on expensive, cloud-based LLMs (like OpenAI), this project is built from scratch using foundational data science techniques. It utilizes a custom **Hybrid Scoring Algorithm** that blends **TF-IDF Cosine Similarity** (for contextual text matching) with **Regex-based Skill Extraction** (for precise technical keyword overlap).

## ✨ Key Features
* **Hybrid ATS Scoring Algorithm**: Weights exact skill overlaps (75%) with contextual TF-IDF text similarity (25%) to provide a highly accurate, human-readable match score.
* **Pure Python NLP**: TF-IDF and Cosine Similarity are built completely from scratch without heavy external machine learning libraries.
* **Smart PDF Parsing**: Extracts clean text from uploaded resumes using `pypdf`.
* **Skill Gap Analysis**: Explicitly lists missing technologies and tools using a customizable `skills.json` dictionary.
* **Actionable Advice**: Auto-generates personalized next steps based on missing skills.
* **Privacy First**: Processes data securely without sending your resume to external AI APIs.

## 🏗️ Architecture & Data Flow
```mermaid
graph TD;
    A[User Inputs Resume & JD] --> B[Text Preprocessor];
    B --> C[Custom TF-IDF Vectorizer];
    C --> D[Cosine Similarity Matcher];
    B --> E[Regex Skill Extraction Engine];
    E --> F[Skill Gap Analysis];
    D --> G[Hybrid Score Calculation];
    F --> G;
    G --> H[Streamlit Dashboard & Recommendations];
