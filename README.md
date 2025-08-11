# Noogat Assignment – AI-powered PowerPoint Inconsistency Checker

## 📌 Overview
This Python-based tool analyzes **multi-slide PowerPoint presentations (`.pptx`)** to detect:
- Conflicting numerical data (e.g., mismatched revenue, wrong percentages)
- Contradictory textual claims
- Timeline/date inconsistencies  
It works on **both text in slides and text extracted from slide images**, using **OCR + LLM (Gemini 2.5 Flash)**.

---

## 🚀 Features
- **PPTX Parsing** – Reads all text from slides using `python-pptx`
- **OCR for Images** – Uses `pytesseract` to detect text from images in slides
- **AI Analysis** – Sends extracted content to Gemini for detecting inconsistencies
- **Structured Output** – Saves:
  - `output/inconsistencies.json` → structured data
  - `output/report.txt` → human-readable summary
- **Generalized Design** – Works for any presentation, not just the sample

---

## 📂 Project Structure
noogat_inconsistency_checker/
│
├── main.py # Main script to run the analysis
├── requirements.txt # Python dependencies
├── .env # Stores your GEMINI API key
├── output/
│ ├── inconsistencies.json
│ └── report.txt
└── README.md # Project documentation

---

## ⚙️ Installation & Setup

1️⃣ **Clone the repository** (or download ZIP)  

git clone https://github.com/YOUR_USERNAME/noogat_inconsistency_checker.git
cd noogat_inconsistency_checker

2️⃣ Install dependencies

pip install -r requirements.txt

3️⃣ Set up your Gemini API key

Create a .env file in the project root:

GEMINI_API_KEY=your_api_key_here

▶️ Usage
Run the script:

python main.py
When prompted, enter the path to your PPTX file:

Enter path to PPTX file: NoogatAssignment.pptx
Results will be saved to:

output/inconsistencies.json (machine-readable)
output/report.txt (human-readable summary)

📊 Example Output
report.txt

Slide 2 & Slide 5 – Revenue mismatch:
Slide 2 states $5M, Slide 5 states $4.2M

Slide 3 & Slide 6 – Contradictory market claim:
Slide 3: "Highly competitive market"
Slide 6: "Few competitors"

🛠 How it Works
Extract slide text – python-pptx parses all text boxes.
Extract image text – pytesseract runs OCR on slide images.
Send to Gemini API – Text data is analyzed for:
Number mismatches
Contradictory claims
Timeline conflicts
Output structured report – Saved in JSON + text format.

📌 Limitations
Accuracy depends on OCR quality for images.
LLM (Gemini) analysis may produce false positives or miss subtle context.
Requires internet connection for API calls.
API usage is subject to Gemini’s token limits.

📅 Submission Info

Built by: Bhanuteja Valaboju

IITM Data Science 

Contact: bhanutejavalaboju07@gmail.com
