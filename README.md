Noogat Assignment – AI-powered PowerPoint Inconsistency Checker
📌 Overview
This Python-based tool analyzes multi-slide PowerPoint presentations (.pptx) to detect factual and logical inconsistencies, such as:
Conflicting numerical data (e.g., mismatched revenue, incorrect percentages)
Contradictory textual claims
Timeline/date mismatches
It processes both text in slides and text extracted from images using OCR + Gemini 2.5 Flash API.

🚀 Features
PPTX Parsing – Reads all slide text using python-pptx
OCR for Images – Extracts text from images in slides with pytesseract
AI-Powered Analysis – Uses Gemini 2.5 Flash to detect:
Numerical inconsistencies
Contradictory statements
Timeline/date mismatches

Structured Output – Saves:
output/inconsistencies.json → machine-readable structured results
output/report.txt → human-readable summary
Generalized Design – Works for any presentation, not just the sample deck

🛠 How It Works
Extract Slide Text – Using python-pptx, all text boxes are read from each slide.
Extract Image Text – pytesseract runs OCR on embedded images in slides.
Send to Gemini API – Combined text is sent to Gemini for analysis.

Detect Inconsistencies – AI checks for:
Conflicting numbers
Contradictory claims
Timeline mismatches
Generate Output – Saves findings in both JSON and plain text for easy review.

📂 Project Structure
bash
Copy
Edit
noogat_inconsistency_checker/
│
├── main.py                # Main script to run the analysis
├── requirements.txt       # Python dependencies
├── .env                    # Stores your GEMINI API key (placeholder, no real key)
├── output/
│   ├── inconsistencies.json
│   └── report.txt
└── README.md               # Project documentation
⚙️ Installation & Setup
Clone the Repository
git clone https://github.com/bhanu07-v/noogat_inconsistency_checker.git
cd noogat_inconsistency_checker


Install Dependencies

pip install -r requirements.txt

Set Your Gemini API Key
Create a .env file in the project root:
GEMINI_API_KEY=your_api_key_here

▶️ Usage
Run the script:
python main.py
When prompted, enter the path to your PPTX file:

Enter path to PPTX file: NoogatAssignment.pptx
📊 Example Output (report.txt)

Slide 2 & Slide 5 – Revenue mismatch:
Slide 2 states $5M, Slide 5 states $4.2M

Slide 3 & Slide 6 – Contradictory market claim:
Slide 3: "Highly competitive market"
Slide 6: "Few competitors"
📌 Limitations
OCR quality may affect detection accuracy for images.

AI analysis can produce false positives or miss subtle context.

Requires internet access for Gemini API calls.

API usage is subject to Gemini’s rate limits.

👤 Author
Bhanuteja Valaboju

IITM Data Science & SR University (ECE)

Email: bhanutejavalaboju07@gmail.com

GitHub: bhanu07-v

📜 License
This project is licensed under the MIT License.

