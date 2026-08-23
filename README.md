# AI Resume to Portfolio Generator

An AI-powered web application that converts a simple text-based resume into a professional and interactive portfolio website. The application uses Gemini AI to understand resume information and generates a personalized portfolio with multiple design themes.

## 🚀 Features

* Transform plain resume text into a complete portfolio website
* Extract and organize resume details using Gemini AI
* Choose from four different portfolio themes:

  * Vivid
  * Bold
  * Editorial
  * Dark
* View the generated portfolio instantly through a live preview
* Keep the selected theme synchronized with the preview
* Try the application with a built-in sample resume
* Handle incomplete or incorrectly formatted AI-generated JSON safely
* Generate portfolios temporarily without permanently storing user data

---

## ⚙️ How It Works

1. **Resume Submission**
   Users can paste their resume content or use the built-in sample resume.

2. **AI Analysis**
   The resume information is sent to the Gemini API, which converts the unstructured text into organized JSON data.

3. **Data Processing**
   The Python backend extracts, checks, and validates the information received from Gemini.

4. **Portfolio Creation**
   The processed resume data is inserted into the portfolio HTML template.

5. **Live Preview**
   The generated portfolio is displayed inside an iframe, allowing users to preview the result and switch themes interactively.

---

## 🏗️ Architecture

```text
                    ┌──────────────────────┐
                    │        User          │
                    │  Resume / Sample     │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │      Frontend        │
                    │ HTML + CSS + JS      │
                    └──────────┬───────────┘
                               │
                         POST /api/generate
                               │
                               ▼
                    ┌──────────────────────┐
                    │    Python Backend    │
                    │   api/generate.py    │
                    │                      │
                    │ • Gemini integration │
                    │ • JSON processing    │
                    │ • Data validation    │
                    │ • HTML generation    │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │      Gemini AI       │
                    │ Resume → JSON        │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │ Portfolio Templates  │
                    │ HTML + CSS Themes    │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │    Live Portfolio    │
                    │       Preview        │
                    └──────────────────────┘
```

---

## 🛠️ Tech Stack

* **Frontend:** HTML, CSS, JavaScript
* **Backend:** Python
* **AI Integration:** Google Gemini API
* **Deployment:** Vercel

---

## 📁 Project Structure

```text
Resume_to_portfolio/
│
├── api/
│   └── generate.py       # Backend API and Gemini integration
│
├── index.html            # Main resume input and preview interface
├── launcher.css          # Styling for the generator interface
├── template.html         # HTML structure for generated portfolios
├── style.css             # Portfolio themes and visual styling
├── resume.txt            # Example resume for testing
├── requirements.txt      # Python package dependencies
├── vercel.json            # Vercel deployment configuration
└── .gitignore            # Files excluded from Git
```

### File Roles

* **`api/generate.py`** – Connects with Gemini, processes the generated response, validates the data, and creates the portfolio HTML.
* **`index.html`** – Contains the main application interface where users enter their resume and access the preview.
* **`launcher.css`** – Controls the appearance of the resume generator and preview area.
* **`template.html`** – Acts as the basic HTML layout used for generated portfolios.
* **`style.css`** – Provides the styling and theme variations for the generated portfolio.
* **`resume.txt`** – Contains sample resume information for testing the application.

---

## 💻 Local Setup

### 1. Clone the Repository

```bash
git clone https://github.com/Aniket-Singh25cp/Resume_To_Portfolio_Generator
cd Resume_to_portfolio
```

### 2. Install Required Packages

Install the dependencies listed in `requirements.txt`:

```bash
pip install -r requirements.txt
```

### 3. Add Your Gemini API Key

Create a `.env` file in the root directory and add your Gemini API key:

```env
GEMINI_API_KEY=your_gemini_api_key
```

> **Important:** Never upload your `.env` file or expose your API key publicly. Make sure `.env` is included in `.gitignore`.

### 4. Start the Application

Run the application using:

```bash
python main.py
```

After starting the server, open the local URL displayed in the terminal.

---

## 🌐 Deployment

This project can be deployed using **Vercel** with its serverless Python API.

The backend endpoint used by the application is:

```text
/api/generate
```

Before deploying, add your `GEMINI_API_KEY` to the environment variables provided by Vercel.

Never store the API key directly inside the source code or commit it to GitHub.
