# AI Recruitment System - Backend

Backend API for an AI-powered recruitment screening system that analyzes candidate CVs, skills, experience, GitHub profiles, and selected job requirements to generate an AI-based candidate-job fit evaluation.

## Features

- Candidate application processing
- PDF CV text extraction
- GitHub profile and repository analysis
- Job-specific candidate evaluation
- AI Fit Score from 0-100
- Candidate classification
- Risk level assessment
- AI recruitment decision
- Missing skills identification
- Supabase database integration
- CV storage in Supabase Storage
- Recruitment dashboard API

## AI Decisions

| Fit Score | Classification | Decision |
|---|---|---|
| 75-100 | Strong Match | Shortlist |
| 45-74 | Needs Review | Human Review |
| 0-44 | Weak Match | Reject |

## Technologies

- Python
- FastAPI
- Groq AI API
- Supabase
- PostgreSQL
- pypdf
- GitHub REST API
- REST APIs
- Uvicorn
- Python Dotenv

## Main API Endpoints

### Health Check

GET /health

### Available Jobs

GET /jobs

### Recruitment Dashboard

GET /dashboard

### Analyze Candidate Application

POST /analyze-application

The application endpoint accepts candidate information, selected position, skills, experience, optional GitHub profile, and a PDF resume.

## Environment Variables

Create a `.env` file in the backend directory.

SUPABASE_URL=your_supabase_project_url  
SUPABASE_KEY=your_supabase_secret_key  
SUPABASE_RESUME_BUCKET=Resumes  

GROQ_API_KEY=your_groq_api_key  
GROQ_MODEL=openai/gpt-oss-20b  

Never commit the `.env` file or API secrets to GitHub.

## Installation

Create a Python virtual environment:

python -m venv venv

Activate it on Windows:

venv\Scripts\activate

Install dependencies:

pip install -r requirements.txt

## Run Backend

python -m uvicorn main:app --reload

Backend URL:

http://127.0.0.1:8000

FastAPI Swagger Docs:

http://127.0.0.1:8000/docs

## Application Flow

Candidate Application
↓
FastAPI Backend
↓
PDF CV Text Extraction
↓
GitHub Profile Analysis
↓
Selected Job Requirements
↓
Groq AI Evaluation
↓
Fit Score + Classification
↓
Decision + Missing Skills
↓
Supabase Database
↓
Frontend Result / Dashboard

## Core Evaluation Inputs

The AI evaluates candidates using:

- Resume / CV content
- Candidate skills
- Years of experience
- Selected job requirements
- GitHub profile
- GitHub repositories
- Programming languages
- Relevant technical evidence

## Security

Sensitive credentials are stored in environment variables and excluded from Git using `.gitignore`.

Excluded files:

.env  
venv/  
__pycache__/  
*.pyc  

## Project Status

Final working version completed and tested.

Git tag:

FINAL-WORKING