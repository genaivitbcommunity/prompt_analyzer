# Training & Dataset

Offline research artifacts for the BERT structural scorer. **Not required** to run the Flask app (`python main.py`).

## Layout

```text
training/
├── README.md
├── data/
│   └── final_clean_bert_data.csv   # Balanced dataset used for BERT regression
└── notebooks/
    ├── dataset_EDA.ipynb           # Cleaning, Tower of 65 analysis, upsampling
    └── model_train.ipynb           # BERT fine-tuning / regression training
```

## Notebooks

| Notebook | Purpose |
|----------|---------|
| `notebooks/dataset_EDA.ipynb` | Exploratory analysis, cleaning, and export of the balanced CSV |
| `notebooks/model_train.ipynb` | Fine-tunes the BERT regressor used as the structural gatekeeper |

These notebooks were written for **Google Colab**-style paths (e.g. `/content/final_clean_bert_data.csv`). When running locally, point load/save paths at:

```text
training/data/final_clean_bert_data.csv
```

## Runtime vs training

| Concern | Location |
|---------|----------|
| Live scoring + improve | Root: `app_flow.py`, `main.py`, `static/`, `templates/` |
| BERT inference API | External HF Space via `BERT_API_URL` |
| Dataset / model training | This `training/` folder only |
