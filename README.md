# media-literacy-bias-ml
Predicting overconfidence in media literacy using Random Forests on RAND ALP survey data

# Evaluating Media-Literacy Bias with Top-2 Random-Forest Predictions

This repository contains my capstone research project at **The Chinese University of Hong Kong (CUHK, 2025)**.  
The study applies Random Forest models on survey data from the **RAND American Life Panel (ALP)**  
to predict individuals who overestimate their resistance to misinformation and disinformation.

---

## Abstract

This study was conducted to predict which individuals are likely to overestimate their resistance to misinformation and disinformation by using machine learning models.  
A Random Forest classifier was applied on survey data from the RAND American Life Panel, containing media-literacy confidence and concern variables to predict perceived personal vulnerability.  
4-class classification with Top-2 predictions achieved **0.71 accuracy**, and weighted models improved minority-class recall.  
The binary weighted model showed **0.67 accuracy** and **0.78 recall**, suggesting the potential for accurate identification of individuals who are overconfident in media literacy and targeted social interventions.

---

## Method Overview

- **Goal:** Predict individuals’ overconfidence in media literacy  
- **Algorithm:** Random Forest Classifier (Breiman, 2001)  
- **Evaluation:** Top-1 / Top-2 accuracy, Precision, Recall, F1-score  
- **Features:** Media literacy confidence (Q4), Concern about misinformation (Q5)  
- **Target:** Personal concern about being misled (Q6)  
- **Class balancing:** `class_weight='balanced'` for minority recall improvement  
- **Validation:** Grid Search + 5-Fold Cross Validation  

---

## Model Variants

| Model | Accuracy | Minority Recall |
|--------|-----------|----------------|
| 4-class, no-weight, Top-1 | 0.42 | 0.15 |
| 4-class, no-weight, Top-2 | 0.71 | 0.38 |
| 4-class, weighted, Top-1 | 0.40 | 0.61 |
| 4-class, weighted, Top-2 | 0.71 | 0.83 |
| Binary collapsed, weighted | 0.67 | 0.78 |

---

## Data Information

Due to RAND’s data-use restrictions, the original dataset is **not included** in this repository.  

- **Source:** RAND American Life Panel (ALP)  
- **Module:** “Media and Misinformation” (Wave 2022-10)  
- **Access:**[https://www.rand.org/research/data/alp.html](https://www.rand.org/research/data/alp.html) 
- **Sample size:** 936 respondents (Completion rate ≈ 72.6%)  
- **Age range:** 55–90+ years  
- **Variables:** Media-literacy confidence (Q4), Concern about misinformation (Q5), Self-concern (Q6)  
- **Data usage note:**  
  Access requires a RAND account. The data used in this project were obtained under CUHK’s 2024 academic license.

---

## How to Run

1. Clone this repository  
   ```bash
   git clone https://github.com/soomorita/media-literacy-bias-ml.git
   cd media-literacy-bias-ml


2. Add the RAND dataset (once obtained) under data/ as alp_misinformation.csv

3. Open the notebook in Jupyter or Colab:
   notebook/media_literacy_bias.ipynb
---

## Author

**Soya Morita**  
The Chinese University of Hong Kong (Exchange, 2024)  
[GitHub](https://github.com/soomorita)

## References

Breiman, L. (2001). Random Forests. Machine Learning, 45(1), 5–32.
Davison, W. P. (1983). The Third-Person Effect in Communication. Public Opinion Quarterly, 47(1), 1–15.
Pronin, E. et al. (2002). The Bias Blind Spot. Personality and Social Psychology Bulletin, 28(3), 369–381.
RAND ALP Data Portal: [https://www.rand.org/research/data/alp.html](https://www.rand.org/education-employment-infrastructure/survey-panels/alp.html)
