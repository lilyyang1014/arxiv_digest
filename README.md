# arxiv_digest
ArXiv LLM Research Digest

I am an automated tool that searches, filters, and summarizes the latest Large Language Model (LLM) research papers from arXiv, with a focus on publications from top institutions.

🌟 Features

✅ Smart Keyword Filtering: Automatically identifies LLM-related papers using predefined keywords ✅ Institution Recognition: Focuses on research from top academic and industry labs ✅ Domain Detection: Identifies papers with authors from prominent research institutions via email domains ✅ PDF Content Analysis: Analyzes paper content to confirm institutional affiliation ✅ AI-Generated Summaries: Uses Gemini 2.0 Flash to generate concise summaries of selected papers ✅ Automatic Report Generation: Creates consolidated markdown reports of filtered papers

📋 How It Works The system follows a multi-stage filtering pipeline:

Initial arXiv Search: Queries arXiv for Computer Science papers updated within a specific date range Keyword Filtering: Identifies papers with LLM-related keywords in titles and abstracts PDF Download: Downloads PDFs for further analysis Affiliation Analysis: Examines PDF headers and author information for target institutions LLM Verification: Uses Gemini to confirm institutional affiliations and generate summaries Report Generation: Creates a consolidated markdown report of all matching papers

🛠️ Configuration The script uses several configuration variables that can be modified:

LLM-related keywords for initial filtering
KEYWORDS = ['llm', 'large language model', 'language model', 'foundation model', 'pretrained language model', 'transformer', 'generative ai' ]

Target date range for paper search (YYYYMMDDHHMMSS format)
TARGET_DATE_START = "20250411000000" TARGET_DATE_END = "20250411235959"

Target institutions for affiliation matching
TARGET_INSTITUTIONS = [ "Stanford", "Stanford University", "Princeton University", "UC Berkeley", "University of California, Berkeley", "Berkeley", "CMU", "Carnegie Mellon University", "Carnegie Mellon", "NVIDIA Research", "NVIDIA", "Google Deepmind", "Deepmind", "Google", "OpenAI", "University of Washington", "Cornell University", "University of Illinois Urbana-Champaign", "UIUC", "Allen Institute for AI", "AI2" ]

📦 Requirements

✅Python 3.7+ ✅Required libraries: arxiv PyMuPDF (fitz) google-generativeai re os time shutil sys

🚀 Installation

Clone this repository: git clone https://github.com/lilyyang1014/arxiv_digest.git

Install dependencies: pip install arxiv pymupdf google-generativeai

Set up your Google API key:

Get a Gemini API key from Google AI Studio Update the GOOGLE_API_KEY variable in the script

Configure your project path:

Update the FIXED_PROJECT_PATH variable to your desired storage location

🔧 Usage Run the script with Python: python arxiv_digest_generator.py

The script will:

Search arXiv for papers matching the date range and keywords Download matching papers to a dated folder Filter papers based on institutional affiliations Generate summaries using the Gemini API Create a consolidated markdown report of the findings

📝 Output The script creates a folder structure with:

A base directory named by the date (MMDDYYYY format) All initially filtered papers in the base directory A "Final_Selected_Papers" subdirectory containing only institution-matched papers A consolidated markdown report with paper details and AI-generated summaries

📊 Example Output

04112025 Consolidated Paper Summaries
Target Institutions for Filtering: Stanford University, Princeton University, UC Berkeley, CMU, University of Washington, Cornell University, UIUC, Google Deepmind, OpenAI, NVIDIA, AI2
Improving Large Language Models' Abilities to Handle Ambiguity
Authors: Jane Doe, John Smith, Alice Johnson

Affiliation Evidence: Email: jdoe@stanford.edu

Summary (Gemini-2-flash Generated): This paper introduces a novel framework for enhancing LLMs' capabilities to handle ambiguous queries through a multi-stage clarification process. The authors demonstrate a 37% improvement in accuracy on ambiguous benchmark tasks compared to baseline models. Their approach combines contrastive learning with explicit uncertainty representation, enabling more effective disambiguation without requiring additional training data.

🔒 Privacy & Ethics This tool is designed for research purposes only. Please respect:

arXiv's terms of service regarding automated downloads Google's API usage policies The intellectual property rights of paper authors

‼️ Please keep your API key in your .env, please do not upload it to github.

📄 License MIT License

🙋‍♀️ Author: Liuying Yang, Wei Li

🤝 Contributing Contributions are welcome! Please feel free to submit a Pull Request.
