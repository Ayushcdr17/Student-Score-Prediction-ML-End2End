# 📊 Maths Score Predictor

An **End-to-End Machine Learning Project** to predict **students’ Maths scores** using demographic and academic features.
The project includes **EDA, ML modeling, Flask web application**, and **multi-cloud deployment** with CI/CD pipelines.

---

## 🚀 Project Lifecycle

1. Problem Understanding
2. Data Collection & Cleaning
3. Exploratory Data Analysis (EDA)
4. Feature Engineering & Preprocessing
5. Model Training (XGBoost, CatBoost, Random Forest, etc.)
6. Flask Web Application
7. Deployment: **AWS Elastic Beanstalk, AWS EC2+ECR, Azure Web App with Containers**
8. CI/CD with **AWS CodePipeline** and **GitHub Actions**

---

## 📂 Dataset

* **Source:** [Kaggle - Students Performance in Exams](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)
* **Rows:** 1000 | **Columns:** 8
* **Target Variable:** `math_score`

---

## 📊 Exploratory Data Analysis

✅ Distribution plots, violin plots, pie charts, heatmaps
✅ Gender vs Scores, Ethnicity vs Scores
✅ Impact of Lunch type, Parental Education, and Test Prep
✅ Correlation between Reading, Writing, and Math scores

**Key Insights:**

* Female students score higher overall, but males perform slightly better in Maths.
* Students with **standard lunch** and **completed test prep** perform better.
* **Parental education** has moderate influence.
* Groups **A & B** tend to score lower.

---

## 🛠️ Tech Stack

* **Python 3.8+**
* Pandas, NumPy, Matplotlib, Seaborn
* Scikit-learn, XGBoost, CatBoost
* Flask (Web Framework)
* AWS (Beanstalk, EC2, ECR, CodePipeline)
* Azure (Container Registry + Web App)
* Docker

---

## 📈 Model Training

* Preprocessing via **ColumnTransformer** (scaling + encoding)
* Algorithms tested: Linear Regression, Ridge, Lasso, Decision Tree, Random Forest, KNN, XGBoost, CatBoost, AdaBoost
* **Best Models:** XGBoost & CatBoost (highest R² score)

---

## 🌐 Flask Web Application

Interactive web app with form inputs:

* Gender
* Ethnicity
* Parental Education
* Lunch Type
* Test Preparation Course
* Writing & Reading Scores

📌 **UI Features:**

* Dark theme with glowing **green-blue border**
* User-friendly form design
* Real-time prediction output

![Score Prediction UI](static\images\image.png)

---

## 📦 Deployment

### ✅ 1. Local Deployment

```bash
python app.py
```

Runs at → `http://127.0.0.1:5000/`

---

### ✅ 2. AWS Elastic Beanstalk

* Added **.ebextensions** config for WSGI entrypoint.
* Created `application.py` as entrypoint.
* Pushed code to GitHub → Connected via **CodePipeline**.
* Automatic deployments from GitHub → Elastic Beanstalk.

🔹 **Pipeline:** GitHub → AWS CodePipeline → Elastic Beanstalk

---

### ✅ 3. AWS EC2 with Docker + ECR

* **Dockerized** app with `Dockerfile`
* Built & pushed image → **AWS ECR**
* Configured **IAM User** with permissions (ECR + EC2)
* Created EC2 instance, installed Docker
* Pulled image from ECR → Deployed container

🔹 **CI/CD with GitHub Actions**:

* On push → Build Docker image
* Push to **ECR**
* SSH into EC2 → Pull & Run latest container

---

### ✅ 4. Azure Deployment with Containers

* Built Docker image locally
* Pushed to **Azure Container Registry (ACR)**
* Created **Azure Web App for Containers**
* Linked to ACR for deployment
* Enabled **Continuous Deployment with GitHub Actions**

---

## 🔄 CI/CD Pipelines

### AWS CodePipeline

* Source: GitHub
* Deploy: AWS Elastic Beanstalk
* Auto-deploys on every push

### GitHub Actions

* Runs **CI/CD workflow**:

  * Lint/Test → Build Docker image → Push to ECR → Deploy on EC2
  * Supports Azure Web App deployment via ACR

---

## 📊 Results

* **XGBoost & CatBoost** gave best performance
* **Flask Web App** deployed successfully across multiple cloud platforms
* CI/CD pipelines automate deployment → no manual redeploys needed

---

## 👩‍💻 Author

**Ayush Payal**


