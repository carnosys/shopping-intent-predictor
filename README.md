# Shopping Intent Predictor (KNN Classifier)

An **AI model that predicts whether an online shopping customer will complete a purchase**, using a **k-nearest neighbors (k=1)** classifier.

The system analyzes user session data (like pages visited, time spent, browser, and weekend activity) and classifies whether the user is likely to make a purchase (`Revenue = TRUE`) or not.

---

## 📊 Example Run

```bash
$ python shopping.py shopping.csv
Correct: 4088
Incorrect: 844
True Positive Rate: 41.02%
True Negative Rate: 90.55%
```

---

## 🛍️ Background

Most visitors to online shopping websites do not complete a purchase.
Predicting **purchase intent** is valuable, e.g., offering discounts to hesitant buyers.

This project applies **machine learning** to:

* Train on \~12,000 shopping sessions (`shopping.csv`).
* Predict if a visitor will complete a purchase.
* Evaluate performance with **sensitivity (true positive rate)** and **specificity (true negative rate)**.

---

## 🤖 AI Approach

* Uses **k-nearest neighbors (k=1)** classifier via `scikit-learn`.
* Input (evidence):

  * Pages visited, time spent, bounce/exit rates, month, OS, browser, traffic type, visitor type, weekend, etc.
* Output (label):

  * `1` = user made a purchase.
  * `0` = user did not.

### Accuracy Metrics

* **Sensitivity (True Positive Rate)** → proportion of buyers correctly predicted.
* **Specificity (True Negative Rate)** → proportion of non-buyers correctly predicted.

---

## 📂 Project Structure

```
.
├── shopping.py   # Main program: loads data, trains, tests, evaluates
├── shopping.csv  # Dataset (~12,000 online shopping sessions)
├── README.md     # Documentation
```

* **load\_data** → loads CSV, converts categorical data to numeric, returns `(evidence, labels)`.
* **train\_model** → trains a KNN classifier (`k=1`).
* **evaluate** → computes sensitivity & specificity.
* **main** → runs the pipeline (train/test split, evaluation, printing results).

---

## 🛠️ Technologies Used

* **Python 3.12**
* **scikit-learn** (KNeighborsClassifier)
* **pandas / numpy** (optional, for preprocessing)

---

## ✨ Features

* Predicts user purchase intent from session data.
* Handles categorical → numeric conversion (month, visitor type, weekend).
* Evaluates model using **sensitivity & specificity**.
* Outputs accuracy statistics after training/testing.

---
