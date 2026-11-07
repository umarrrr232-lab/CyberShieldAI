# CyberShieldAI

I just finished CyberShield AI, a full-stack machine learning web app for cybersecurity threat detection, built with my teammates [@names] for our ML lab.

It runs 4 models behind one FastAPI backend:
- Network traffic: Random Forest that tells normal traffic from 4 types of DoS attack
- Web addresses: Decision Tree that flags phishing URLs
- Email: Logistic Regression + TF-IDF that sorts ham, spam and phishing
- Connection length: Linear Regression that estimates how long a connection lasts

What I learned the hard way:
- Data leakage is everywhere. Columns like packets-per-second quietly contain the answer, so we removed them instead of chasing a fake high score.
- Duplicate rows must be removed before the train/test split, or your test score lies.
- Accuracy alone hides weak classes, so we checked macro F1 and confusion matrices.
- Logging skewed inputs took our regression R² from 0.23 to 0.53.

Limits: it is trained on lab datasets, so it is a learning project, not a production security tool.

Stack: Python, scikit-learn, FastAPI, HTML/CSS/JavaScript.
Code: [GitHub link]

#MachineLearning #Cybersecurity #FastAPI #scikitlearn #DataScience
