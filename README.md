# StereotAIps: Gender Bias Analysis in Language Models

>  **University Project – Machine Learning @ UNIBO**  
> This repository contains the final assignment for the **Machine Learning course** at the **University of Bologna (UNIBO)**.  
> The project investigates **gender bias in AI language models**, with a focus on the **BERT architecture** and its tendency to reflect societal stereotypes.  
>  
> **Deadline**: within one week from assignment date.

---

## Project Overview

- **Objective**: Analyze and quantify gender bias in pretrained Language Models (LMs), specifically **BERT**.
- **Scope**: Assess whether predictions made by BERT reflect **societal gender stereotypes**, especially those targeting women.
- **Approach**: Use a **Masked Language Model (MLM)** setup with sentence templates targeting both male- and female-oriented subjects.

---

## Methodology

### 1. Language Models Used
- `BERTbase` (110M parameters)
- `BERTlarge` (340M parameters)

### 2. Test Templates
- **Role Test**: Measures bias between high- and low-specialization professions.
- **Societal Test**: Evaluates verbs/adjectives generated for different gender targets.
- **Open Roles Test**: Analyzes open-ended completions to identify harmful terms or stereotypes.

### 3. Evaluation Tools
- **Sexism Detector**: A model trained to classify sexist content.
- **Hurtlex**: A multilingual lexicon of offensive and biased terms.
- **Sentiment Analysis**: Uses AFINN lexicon to score word connotation (from -5 to +5).

---

## Dataset

- Generated 521 template-based sentences based on prior academic works (e.g., Nozza et al., 2022).
- Templates were adapted to combine masked sentences with gender-specific subjects:
  - Example: `<target> dreams of being a [MASK]` with targets like `she/he`, `her/him`, `mum/dad`.

---

## Key Findings

- **Bias Detection**: Significant presence of gender bias in BERT outputs.
- **Sexist Labels**: Female-oriented subjects were more likely to produce sexist or stereotyped sentences.
- **Hurtful Language**: Terms related to prostitution and derogatory language occurred more frequently with female subjects.
- **Model Scaling**: BERTlarge tended to amplify bias compared to BERTbase.

---

## Visualizations & Analysis

- Frequency graphs for low/high-specialization professions.
- Distribution of hurtful words by Hurtlex categories.
- Sentiment distribution across gender-based predictions.

---

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/stereotAIps.git
   cd stereotAIps
   ```

2. (Optional) Set up a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use .\venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Run the main script or explore the notebook:
   ```bash
   jupyter notebook
   ```

---

## File Structure

```
.
├── StereotAIps_Notebook.ipynb
├── README.md
├── requirements.txt
└── results/
```

---

## Requirements

- Python 3.8+
- Transformers (HuggingFace)
- Torch
- Pandas
- NumPy
- Matplotlib / Seaborn
- NLTK or TextBlob (for sentiment)
- Jupyter Notebook

---

## License

This project is licensed under the MIT License.

---

## Acknowledgments

- [BERT (Devlin et al., 2018)](https://arxiv.org/abs/1810.04805)
- [StereoSet Dataset](https://github.com/moinnadeem/StereoSet)
- [Hurtlex Lexicon](https://github.com/valeriobasile/hurtlex)
- [Sexism Detector](https://github.com/StereotAIps/SexismDetector)
