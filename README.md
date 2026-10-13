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

**2. Report all 8 coefficients of the **Canonical L2 (Ridge) Model**.**

**3. Report the **Canonical L2 Model's** train and test accuracy. How do they compare to the plain model's from Question 1?**

**4. Report all 8 coefficients of the **Canonical L1 (Lasso) Model**, and name exactly which feature(s) were driven to zero.**

**5. Report the **Canonical L1 Model's** train and test accuracy.**

**6. In your own words, explain the key difference between how **L2** and **L1** treat coefficients as λ grows, based on what you saw in the bar charts.**

**7. True or False: the unregularized model's 100% training accuracy means it's the best model to actually deploy for predicting churn on new customers. Justify your answer using the actual numbers from Question 1.**

**8. Name one **real business or IT scenario** (other than churn prediction) where a classification model could overfit due to too many irrelevant features. Which regularization type (L1 or L2) would you reach for first, and why?**


# References:
- [Streamlit documentation](https://docs.streamlit.io/)
- [Markdown Guide](https://www.markdownguide.org/basic-syntax/)
