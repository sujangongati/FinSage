FinSage – A Multi-aspect RAG System for Financial Filings Question Answering
📌 Overview
FinSage is an advanced Retrieval-Augmented Generation (RAG) framework tailored for financial filings and regulatory compliance analysis.
It integrates multi-modal data processing, multi-path retrieval, and domain-specific re-ranking to provide accurate, compliance-critical answers from complex financial documents.

✨ Key Features
Multi-Modal Pre-processing Pipeline (FFP)
Converts text, tables, and figures from financial PDFs into machine-readable text chunks with semantic enhancements.

Multi-Path Retrieval (MPR)
Combines BM25, dense retrieval, metadata-based search, and HyDE query expansion to improve recall and precision.

Domain-Specific Document Re-Ranker (DRR)
Fine-tuned using Direct Preference Optimization (DPO) to prioritize legally significant content.

High Accuracy
Achieves 92.51% recall and surpasses the best baseline on FinanceBench by 24.06%.

📂 Project Structure
bash
Copy
Edit
.
├── data/                  # Financial filings, PDFs
├── src/                   # Core source code
│   ├── preprocessing/     # Financial Filings Pre-processing (FFP)
│   ├── retrieval/         # Multi-path retrieval (MPR)
│   ├── reranking/         # Document re-ranking (DRR)
│   ├── utils/             # Utility scripts
├── tests/                 # Unit tests
├── README.md              # Project documentation
└── requirements.txt       # Python dependencies
⚙️ Installation
bash
Copy
Edit
# Clone repository
git clone https://github.com/<your-username>/FinSage.git
cd FinSage

# Create virtual environment
python -m venv venv
source venv/bin/activate   # For Linux/Mac
venv\Scripts\activate      # For Windows

# Install dependencies
pip install -r requirements.txt
🚀 Usage
1. Preprocess Financial Documents
bash
Copy
Edit
python src/preprocessing/run_ffp.py --input data/filings/ --output data/processed/
2. Build Vector Store
bash
Copy
Edit
python src/retrieval/build_vector_store.py --input data/processed/
3. Run Question Answering
bash
Copy
Edit
python main.py --query "What was the revenue in Q3 2024?"
📊 Performance
Dataset	LLM Accuracy	Manual Accuracy
FinanceBench	49.66%	57.05%
Company Data	85.33%	88.00%

FinSage significantly outperforms existing RAG systems in financial QA accuracy.

📖 Citation
If you use this work, please cite:

graphql
Copy
Edit
@article{wang2025finsage,
  title={FinSage: A Multi-aspect RAG System for Financial Filings Question Answering},
  author={Wang, Xinyu and Chi, Jijun and Tai, Zhenghan and Kwok, Tung Sum Thomas and Li, Muzhi and et al.},
  journal={arXiv preprint arXiv:2504.14493},
  year={2025}
}
📜 License
This project is licensed under the MIT License.
