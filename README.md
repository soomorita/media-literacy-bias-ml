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

---

## Author

**Soya Morita**  
The Chinese University of Hong Kong (Exchange, 2024)  
[GitHub](https://github.com/soomorita)

## References

- Adele Cutler, D. Richard Cutler, and John R. Stevens. (2012). Random Forests, Ensemble Machine Learning, pp. 157-175.
- Alicke, M. D., Klotz, M. L., Breitenbecher, D. L., Yurak, T. J., & Vredenburg, D. S. (1995). Personal contact, individuation, and the better-than-average effect. Journal of Personality and Social Psychology, 68(5), 804–825.
- Benjamin Enke, Uri Gneezy, Brian Hall, David Martin, Vadim Nelidov, Theo Offerman, Jeroen van de Ven. (2023). Cognitive Biases: Mistakes or Missing Stakes?. The Review of Economics and Statistics 2023; 105 (4): 818–832.
- Breiman, L. (2001) Random Forests. Machine Learning, 45, 5-32.
- Lee, N. M. (2018). Fake news, phishing, and fraud: A call for research on digital media literacy education beyond the classroom. Communication Education, 67(4), 460–466.
- Lee, T. (2019), "The global rise of “fake news” and the threat to democratic elections in the USA", Public Administration and Policy: An Asia-Pacific Journal, Vol. 22 No. 1, pp. 15-24.
- Moore, D. A., & Healy, P. J. (2008). The trouble with overconfidence. Psychological Review, 115(2), 502–517.
- Pronin, E., Lin, D. Y., & Ross, L. (2002). The bias blind spot: Perceptions of bias in self versus others. Personality and Social Psychology Bulletin, 28(3), 369–381.
- Ruggeri, K., Ashcroft-Jones, S., Abate Romero Landini, G. et al. (2023). The persistence of cognitive biases in financial decisions across economic groups. Sci Rep 13, 10329.
- W. PHILLIPS DAVISON. 1983. The Third-Person Effect in Communication. Public Opinion Quarterly, Volume 47, Issue 1, SPRING 1983, Pages 1–15.
- RAND ALP Data Portal: [https://www.rand.org/research/data/alp.html](https://www.rand.org/education-employment-infrastructure/survey-panels/alp.html)
