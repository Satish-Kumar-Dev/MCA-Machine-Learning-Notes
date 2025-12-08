📘 Machine Learning Notes
🗓️ Date: 08/12/2025
🐍 Important Python Libraries for Machine Learning
| Library                    | Purpose                                                                      |
| -------------------------- | ---------------------------------------------------------------------------- |
| **NumPy**                  | Numerical computing, arrays, matrix operations, fast scientific calculations |
| **Pandas**                 | Data manipulation & cleaning using DataFrames                                |
| **Matplotlib**             | Data visualization through plots                                             |
| **Scikit-Learn (sklearn)** | Machine Learning models, preprocessing, model evaluation                     |
Example Code:
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression
📊 Linear Equation & Linear Models
Linear equation shows relationship between dependent & independent variables.

📌 Example:

Price increases when quantity increases.
Linear Regression Equation: y=mx+b
y → Dependent variable (Output/Target)

x → Independent variable (Input/Feature)

m → Coefficient/Slope

b → Intercept

📌 Multiple Linear Regression: y (price) = m1*(area) + m2*(bedrooms) + m3*(age) + b

🔄 Data Processing: Handling Missing Values

When dataset has null values → ML cannot learn properly.

Techniques:

| Method                | When to Use                |
| --------------------- | -------------------------- |
| Remove rows           | If only few values missing |
| Fill with mean/median | Numerical data             |
| Fill with mode        | Categorical data           |

Pandas Example:

df = pd.read_csv("data.csv")
df.fillna(df.mean(), inplace=True)

📈 Linear Regression Using Multiple Variables

Training data → find the line/plane that best fits data.

sklearn Example:

X = df[['area', 'bedrooms', 'age']]
y = df['price']

model = LinearRegression()
model.fit(X, y)

print("Coefficients:", model.coef_)
print("Intercept:", model.intercept_)

🔻 Gradient Descent & Cost Function
📌 Gradient Descent
Algorithm that finds best-fit line by reducing error step-by-step.

Cost Function (Mean Squared Error - MSE): J(m,b)=1/2m∑(ypred−y)2

Goal → minimize J

Derivative Rule Example (from your request)

📌 Derivative of x^2: dxd(x^2)=2x
	Update Rule: m=m−α∂m∂J​
				b=b−α∂b∂J​
	(α = Learning Rate)
💾 Saving a Trained Model
	Using Pickle:
		import pickle
		pickle.dump(model, open('model.pkl', 'wb'))
	Using Joblib:
		from joblib import dump
		dump(model, 'model.joblib')
🔠 One-Hot Encoding (Dummy Variables)
	Used for categorical data (e.g., Country → India, USA, UK):
		df = pd.get_dummies(df, columns=['Country'], drop_first=True)
		
		
📌 Dummy Variable Trap

Highly correlated columns lead to multicollinearity

Better to drop one column (drop_first=True)

✂️ Train-Test Split
	Used to check how model performs on unseen data.:
		from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42)

🔒 Logistic Regression:
	Used for classification (Yes/No, Spam/Not Spam)

	Sigmoid Function: σ(z)=1+e−z1​
	Converts value into probability (0 to 1):
		from sklearn.linear_model import LogisticRegression

		log_model = LogisticRegression()
		log_model.fit(X_train, y_train)
	📌 Supports binary & multi-class classification
	
📌 Reference for Calculus


	👉 YouTube Channel: 3Blue1Brown
	👉 Website: MathIsFun
	
⭐ End of Notes — 08/12/2025