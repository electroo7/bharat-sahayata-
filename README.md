<div align="center">

# 🇮🇳 BharatSahayata (भारत सहायता)
### Intelligent Government Scheme Discovery & AI Comparison Platform

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg?logo=python&logoColor=white)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-3.0%2B-black.svg?logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![Gemini](https://img.shields.io/badge/Google%20Gemini-2.5%20Flash-orange.svg?logo=google&logoColor=white)](https://aistudio.google.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-brightgreen.svg)]()

**BharatSahayata** empowers Indian citizens, farmers, artisans, students, and entrepreneurs by simplifying access to central and state government schemes through **algorithmic profile matching** and an **AI-powered objective scheme comparison assistant**.

</div>

---

## 📌 Table of Contents
- [Overview](#-overview)
- [Key Features](#-key-features)
- [Algorithm & Matching Engine](#-algorithm--matching-engine)
- [AI Scheme Comparison Assistant](#-ai-scheme-comparison-assistant)
- [Tech Stack](#-tech-stack)
- [Project Directory Structure](#-project-directory-structure)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation & Setup](#installation--setup)
  - [Environment Variables](#environment-variables)
  - [Running the Application](#running-the-application)
- [API Reference](#-api-reference)
- [Verified Schemes Included](#-verified-schemes-included)
- [Ethical AI & Legal Disclaimer](#-ethical-ai--legal-disclaimer)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🌟 Overview

Navigating India's hundreds of central and state welfare initiatives can be overwhelming due to complex eligibility rules, fragmented ministerial portals, and confusing jargon. 

**BharatSahayata** solves this with a two-step approach:
1. **Algorithmic Profiling**: Evaluates citizen inputs against a weighted 100-point scoring algorithm to instantly recommend qualifying schemes.
2. **AI Comparison Assistant**: When citizens are unsure between two matched schemes (e.g., *PMEGP vs PMMY Mudra* or *PMKVY vs PM Vidyalaxmi*), an integrated Google Gemini 2.5 Flash agent breaks down their differences in a side-by-side matrix with zero bias and zero invented information.

---

## ✨ Key Features

- **🎯 Weighted 100-Point Matching Engine**: Evaluates occupation, purpose, family income, age, geographical scope, and social category without storing private data.
- **🤖 AI Scheme Comparison Assistant**: Powered by **Google Gemini 2.5 Flash** with deterministic dataset fallback in case of missing keys or network limits.
- **⚖️ Side-by-Side Comparison Matrix**: Formatted comparison table comparing purpose, financial benefits, eligibility criteria, and required documents.
- **💬 Conversational Q&A**: Ask custom follow-up questions in natural English or Hinglish without losing comparison context.
- **⚡ Instant Suggested Questions**: One-click prompt pills (*"What is the main difference?"*, *"Compare eligibility"*, *"What documents are required?"*).
- **🛡️ Strict Neutrality & Fact-Grounding**: Built-in guardrails prevent biased advice or declaring false eligibility.
- **🔗 Official Ministry Links**: Direct verified portal links for each scheme so citizens can verify and apply directly.
- **📱 Responsive Indian Design System**: Modern UI styled in Warm Cream, Indian Green (`#16A34A`), Saffron Accent (`#EA580C`), and Midnight Navy (`#0F172A`).

---

## 🧠 Algorithm & Matching Engine

The matching engine in `bharat-sahayata/js/script.js` evaluates citizen inputs against each scheme record using a strict **100-point scoring framework**:

| Criteria | Maximum Weight | Description |
|---|:---:|---|
| **Occupation** | 25 Points | Exact matches receive 25 points; entrepreneurial/student affinities receive partial credit (15–20 pts). |
| **Purpose** | 25 Points | Direct purpose alignment (e.g. "Start a Business", "Agriculture", "Education"). |
| **Family Income** | 20 Points | Compares income tier against designated scheme thresholds. |
| **Age** | 10 Points | Strict boundary check (`minAge <= age <= maxAge`). |
| **Geographic Scope** | 10 Points | "All India" or explicit state residency match. |
| **Social Category** | 10 Points | Open to General / SC / ST / OBC / designated categories. |

### Classification Thresholds:
- **Strong Match (70–100%)**: Highlighted with green indicators and listed at the top.
- **Potential Match (40–69%)**: Highlighted with saffron indicators for consideration.
- **Below 40%**: Excluded from recommended results to minimize noise.

---

## 🤖 AI Scheme Comparison Assistant

The assistant is strictly an **informational comparison tool**, designed to help citizens understand objective differences.

### Core Safeguards:
1. **Never Recommends**: Never declares one scheme as "better" than another.
2. **Never Guarantees Eligibility**: Informs citizens that final decisions rest with the sanctioning ministry/bank.
3. **No Hallucination**: Uses strictly verified dataset parameters and official ministry documentation.
4. **Dual Engine**: If no `GEMINI_API_KEY` is provided, the platform automatically switches to an internal factual compiler, ensuring **100% offline availability**.

---

## 🛠️ Tech Stack

- **Backend**: Python 3.10+, Flask, Requests, Python-Dotenv
- **AI Model**: Google Gemini 2.5 Flash (`gemini-2.5-flash`) via REST API
- **Frontend**: Vanilla HTML5, CSS3 Modern Flex/Grid, Modern Vanilla JavaScript (ES6+)
- **Typography & Icons**: Plus Jakarta Sans, Inter, System Emojis
- **Security**: Server-side API key handling, strict CORS/CSP compliance

---

## 📂 Project Directory Structure

```
GovtScheme/
├── .env.example             # Template for local environment configuration
├── .gitignore               # Excludes secrets, venv, and cache
├── LICENSE                  # MIT Open Source License
├── README.md                # Comprehensive documentation
├── requirements.txt         # Python dependencies
├── server.py                # Flask server & Gemini API integration
└── bharat-sahayata/         # Frontend web application
    ├── index.html           # Main application HTML & Modals
    ├── css/
    │   └── style.css        # Visual design system & responsive styling
    ├── js/
    │   ├── schemes.js       # Verified Indian government schemes dataset
    │   └── script.js        # Core matching engine & comparison controller
    └── assets/              # Logos and SVGs
```

---

## 🚀 Getting Started

### Prerequisites
- **Python 3.10+** installed on your system.
- *(Optional)* A free **Google Gemini API Key** from [Google AI Studio](https://aistudio.google.com/app/apikey).

### Installation & Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/bharat-sahayata.git
   cd bharat-sahayata
   ```

2. **Create and activate a virtual environment**:
   - **Windows (PowerShell)**:
     ```powershell
     python -m venv venv
     .\venv\Scripts\Activate.ps1
     ```
   - **macOS / Linux**:
     ```bash
     python3 -m venv venv
     source venv/bin/activate
     ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

### Environment Variables

Copy `.env.example` to create your `.env` file:
```bash
cp .env.example .env
```

Open `.env` and configure:
```env
# Google Gemini API Key (Optional: Factual dataset fallback works without it)
GEMINI_API_KEY=your_actual_api_key_here

# Server Port
PORT=5000
```

### Running the Application

Start the Flask server:
```bash
python server.py
```

Open your browser and navigate to:
```
http://localhost:5000
```

---

## 📡 API Reference

### `POST /api/compare-schemes`
Compares two government schemes and returns an objective analysis.

#### Request Body:
```json
{
  "scheme1": {
    "id": "pmegp",
    "name": "Prime Minister Employment Generation Programme",
    "category": "Business",
    "purposes": ["Start a Business"],
    "assistance": "Subsidy up to ₹50 Lakhs",
    "basicEligibility": "Age 18+ years, min 8th pass",
    "officialSource": "https://www.kviconline.gov.in/"
  },
  "scheme2": {
    "id": "pm-mudra",
    "name": "Pradhan Mantri Mudra Yojana",
    "category": "Business",
    "purposes": ["Start a Business", "Expand a Business"],
    "assistance": "Collateral-free loan up to ₹10 Lakhs",
    "basicEligibility": "Non-farm income generating enterprises",
    "officialSource": "https://www.mudra.org.in/"
  },
  "question": "What is the main difference?",
  "history": []
}
```

#### Response (200 OK):
```json
{
  "success": true,
  "type": "structured",
  "data": {
    "summary": "Both PMEGP and Mudra support self-employment...",
    "comparison": [
      {
        "category": "Purpose & Objectives",
        "scheme1": "Supports setting up new micro-enterprises...",
        "scheme2": "Supports small businesses with working capital..."
      }
    ],
    "important_note": "Government guidelines are subject to periodic revision...",
    "sources": [
      { "name": "PMEGP", "url": "https://www.kviconline.gov.in/" },
      { "name": "Mudra", "url": "https://www.mudra.org.in/" }
    ],
    "is_ai": true
  }
}
```

---

## 📋 Verified Schemes Included

- **Business & MSME Loans**:
  - *Pradhan Mantri Mudra Yojana (PMMY)*
  - *Prime Minister Employment Generation Programme (PMEGP)*
  - *Stand-Up India Scheme*
  - *Credit Guarantee Fund Trust for Micro and Small Enterprises (CGTMSE)*
  - *PM SVANidhi (Street Vendors AtmaNirbhar Nidhi)*
- **Artisans & Traditional Trades**:
  - *PM Vishwakarma Scheme*
- **Agriculture & Farmers**:
  - *PM-KISAN (Pradhan Mantri Kisan Samman Nidhi)*
  - *Kisan Credit Card (KCC) Scheme*
  - *Pradhan Mantri Fasal Bima Yojana (PMFBY)*
  - *Agriculture Infrastructure Fund (AIF)*
- **Education & Skill Development**:
  - *PM Vidyalaxmi / Vidya Lakshmi Higher Education Scheme*
  - *Pradhan Mantri Kaushal Vikas Yojana (PMKVY 4.0)*
- **Affordable Housing**:
  - *Pradhan Mantri Awas Yojana - Urban (PMAY-U 2.0)*
  - *Pradhan Mantri Awas Yojana - Gramin (PMAY-G)*

---

## ⚖️ Ethical AI & Legal Disclaimer

> **Official Disclaimer:** BharatSahayata recommendations and comparisons are provided for informational and educational awareness purposes only. BharatSahayata does not guarantee scheme approval or financial disbursal. Final eligibility and approvals are solely determined by respective Government Ministries, Departmental Agencies, and lending institutions. Citizens must verify the latest eligibility criteria and procedures through official portals before applying.

---

## 🤝 Contributing

Contributions are welcome! To contribute:
1. Fork this repository.
2. Create a feature branch: `git checkout -b feature/NewSchemeIntegration`.
3. Commit your changes: `git commit -m "feat: add PM Surya Ghar scheme"`.
4. Push to the branch: `git push origin feature/NewSchemeIntegration`.
5. Open a Pull Request.

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.
