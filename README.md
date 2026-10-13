# Activity 14: ShopSmart — Predicting Customer Churn (Regularized Logistic Regression)
## Sessions 24
## Due date (mm/dd/yyyy): 10/18/2026
## Adriana Rosales González
## Delivery Format: [] Video URL | [X] Markdown file | [] Jupyter Notebook file
---

## The Story

**ShopSmart** (the fictional online store from Activity 8) wants to predict which customers are
about to **churn** — cancel their account or simply stop buying. The data team gave you 4
genuinely useful behavioral signals (how long they've been a customer, how much they spend,
how many support tickets they've filed, how long since their last purchase) plus 4 that are
almost certainly useless (favorite color, a "lucky number," signup day of week, referral code
length) — and only 20 training customers to learn from.

---
### Your Tasks

**1. **In the Overfitting Problem tab**, note the training accuracy vs. test accuracy, and the  training loss vs. test loss. Take a screenshot.**

<img width="622" height="616" alt="Captura de pantalla 2026-10-12 185328" src="https://github.com/user-attachments/assets/e8bdbafd-de62-4264-9975-6816fb4d513a" />

**Values:**

**- Train accuracy:** 100%

**- Test accuracy:** 77%

**- Train loss:** 0.022

**- Test loss:** 2.887


---

2. **In the L2 tab, try at least 3 different λ values.** Take a screenshot at a large λ (0.5+).

- Value: 0.08
<img width="620" height="608" alt="image" src="https://github.com/user-attachments/assets/f1af0c8b-a771-4619-b136-f258211aa94e" />


- Value: 0.3
<img width="629" height="603" alt="image" src="https://github.com/user-attachments/assets/350f4ae7-73b7-4ff2-beb3-a13a1ad450d6" />


- Values: 0.85
<img width="622" height="604" alt="image" src="https://github.com/user-attachments/assets/95981ade-93e1-4fa3-bec0-483b3dde6537" />

---
3. **In the L1 tab, try at least 3 different λ values**, and find one where at least 3 features get zeroed out. Take a screenshot.

- Value: 0.05
<img width="627" height="602" alt="image" src="https://github.com/user-attachments/assets/9cb9dfac-3166-4daa-a290-971177919797" />

- Value: 0.20
<img width="620" height="602" alt="image" src="https://github.com/user-attachments/assets/320aebd8-71d1-4349-af0f-d1341cd92311" />


- Value: 0.45
<img width="631" height="533" alt="image" src="https://github.com/user-attachments/assets/1854bd34-8128-45ca-a38d-a8281a8d9105" />

---
4. **Record the Canonical L2 Model's coefficients, train accuracy, and test accuracy.** Take a screenshot.

 - Canonical Ridge Model Values: Train accuracy = 95% ; Test accuracy = 83%
<img width="614" height="509" alt="image" src="https://github.com/user-attachments/assets/f046f98e-81f4-4820-8889-22dee88b2ace" />

---
5. **Record the Canonical L1 Model's coefficients, train/test accuracy, and which features got zeroed out.** Take a screenshot.

 - Canonical Ridge Model Values: Train accuracy = 95% ; Test accuracy = 83% ; Features zeroed out = 5/8
<img width="619" height="535" alt="image" src="https://github.com/user-attachments/assets/a75050b6-dfca-4390-9454-67e178f16e72" />


---
6. **Fill out `A14_ReflectionQuestions.md`**, using the exact numbers from your Canonical Model screenshots, and submit it along with your labeled screenshots.
# Activity 14 — Reflection Questions: ShopSmart Churn Prediction

**1. For the **plain (unregularized) model**, report the train accuracy, test accuracy, train loss, and test loss.**


Plain (unregularized) model
- Train accuracy: **100%**
- Test accuracy: **77%**
- Train loss: **0.022**
- Test loss: **2.887**

The model memorized the training set (100% accuracy) but generalized poorly (much lower test accuracy and very high test loss).
The plain logistic regression model fits the training data perfectly, reaching 100% accuracy and almost zero loss. However, this is a textbook case of overfitting: the model memorized the training set but failed to generalize. The test accuracy drops to 77%, and the test loss is more than 130 times higher than the training loss. This shows the model is not reliable for predicting churn in new customers.

---

**2. Report all 8 coefficients of the Canonical L2 (Ridge) Model**

Canonical L2 (Ridge) Model — Coefficients (λ = 0.05)
- Tenure (months as a customer): ≈ -2.0  
- Average monthly spend ($): ≈ +0.4  
- Support tickets filed: ≈ +0.3  
- Days since last purchase: ≈ +0.2  
- Favorite color (code): ≈ 0.0  
- Customer’s “lucky number”: ≈ 0.0  
- Day of week they signed up: ≈ 0.0  
- Length of referral code: ≈ 0.0  

L2 regularization shrinks all coefficients smoothly toward zero. The important behavioral features (tenure, spend, tickets, recency) remain with meaningful values, while the irrelevant “noise” features are reduced close to zero. This prevents the model from relying on random correlations.

---

**3. Report the **Canonical L2 Model's** train and test accuracy. How do they compare to the plain model's from Question 1?**

- Train accuracy: **95%**
- Test accuracy: **83%**

Compared to the plain model (100% / 77%), the L2 model sacrifices a small amount of training accuracy but gains significantly in test accuracy (+6 points). This demonstrates **better generalization**: the model is less perfect on the training set but more trustworthy on unseen data.

---

**4. Report all 8 coefficients of the **Canonical L1 (Lasso) Model**, and name exactly which feature(s) were driven to zero.**

 Canonical L1 (Lasso) Model — Coefficients (λ = 0.05)
 
- Tenure (months as a customer): ≈ -2.0  
- Average monthly spend ($): **0 (zeroed out)**  
- Support tickets filed: ≈ +0.3  
- Days since last purchase: ≈ +0.2  
- Favorite color (code): **0 (zeroed out)**  
- Customer’s “lucky number”: **0 (zeroed out)**  
- Day of week they signed up: **0 (zeroed out)**  
- Length of referral code: **0 (zeroed out)**  

**Zeroed-out features:** Average monthly spend, Favorite color, Lucky number, Day of week signup, Referral code length.  
L1 regularization performs **automatic feature selection** by driving irrelevant coefficients exactly to zero, leaving only the most predictive variables active.

---

**5. Report the **Canonical L1 Model's** train and test accuracy.**

Canonical L1 Model — Performance
- Train accuracy: **95%**
- Test accuracy: **73%**

The L1 model achieves similar training accuracy as L2 but slightly lower test accuracy. This is because it aggressively eliminates features, which can simplify the model but sometimes remove borderline useful variables. Still, it highlights the most important predictors clearly.

---

**6. In your own words, explain the key difference between how **L2** and **L1** treat coefficients as λ grows, based on what you saw in the bar charts.**

Key difference between L2 and L1
- **L2 (Ridge):** shrinks all coefficients gradually. No feature is eliminated completely, but noise features become very small. This is useful when many features may contribute a little.  
- **L1 (Lasso):** forces some coefficients to exactly zero, effectively removing those features. This is useful when we suspect only a few features are truly relevant.  
In the charts, L2 reduced the red bars smoothly, while L1 erased several bars entirely.

---

**7. True or False: the unregularized model's 100% training accuracy means it's the best model to actually deploy for predicting churn on new customers. Justify your answer using the actual numbers from Question 1.**

- **False.**  

The unregularized model’s 100% training accuracy looks impressive, but it is misleading. Its test accuracy is only 77% and test loss is extremely high (2.887). This proves it does not generalize well. A deployable model must perform well on unseen data, so the unregularized model is not suitable for predicting churn in real business scenarios.

---

**8. Name one **real business or IT scenario** (other than churn prediction) where a classification model could overfit due to too many irrelevant features. Which regularization type (L1 or L2) would you reach for first, and why?**

A clear example is **fraud detection in banking transactions**. If the model includes irrelevant features (like the customer’s browser theme, or the exact minute of login), it may overfit to noise patterns.  
- In such a case, **L1 (Lasso)** would be my first choice because it automatically eliminates irrelevant variables, simplifying the model and focusing only on the strongest predictors.  
- L2 could also help, but L1 is especially powerful when we want to reduce the feature set and avoid spurious correlations.

---

# References:
- [Streamlit documentation](https://docs.streamlit.io/)
- [Markdown Guide](https://www.markdownguide.org/basic-syntax/)
