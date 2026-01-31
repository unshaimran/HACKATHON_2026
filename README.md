Student Dropout Early Warning System – Short Report
1️⃣ Data Cleaning (How data clean kiya)

Dataset: xAPI-Edu-Data

Class column ko target banaya:

L → Dropout (1)

M / H → Continue (0)

Original Class column drop kar di

Missing values check ki:

Dataset me missing values nahi the, is liye fill karne ki zarurat nahi pari

Categorical columns (Gender, Topic, Semester, etc.) ko numeric me convert kiya using factorization

StudentAbsenceDays ko bhi numeric form me convert kiya

2️⃣ Features Used (Konse features use kiye)

Main features jo use hue:

Gender

Nationality

StageID

GradeID

Topic

Semester

Relation

ParentAnsweringSurvey

ParentschoolSatisfaction

StudentAbsenceDays

RaisedHands

VisitedResources

AnnouncementsView

Discussion

Ye sab featureearly-semester behavior dikhate hain, jo early warning ke liye important hai.

3️⃣ Model Choice + Metrics (Model aur accuracy)
Model Type

Traditional ML (sklearn) use nahi kiya

Rule-based + probability-based risk scoring system banaya

Reason:

Beginner-friendly

Easy to explain to non-technical advisors

Transparent decision making

Metrics

Accuracy manually calculate ki:

accuracy = correct_predictions / total_students


Focus accuracy se zyada high-risk students ko identify karna tha

4️⃣ Risk Thresholds (Risk labels kaise banaye)

Risk score continuous value hoti hai.
Usko 3 categories me divide kiya:

Risk Score Range	Risk Label
Low score	Low Risk
Medium score	Medium Risk
High score	High Risk

Code logic:

pd.cut() use kiya

Thresholds dataset ke risk_score distribution ke basis par set kiye

5️⃣ Reasons Behind Dropout Prediction (Dropout ke reasons)

System har student ke liye risk calculate karta hai based on:

High absence days

Low parent school satisfaction

Low participation (raised hands, discussion)

Low resource usage

Low announcement views

Ye reasons advisors ko clearly dikhate hain student kis wajah se risk me hai.

6️⃣ Final Output

Project ye outputs generate karta hai:

risk_score

risk_label (Low / Medium / High)

predicted_dropout (0 / 1)

Top 20 high-risk students list

CSV file: student_risk_predictions.csv

Streamlit dashboard for visualization

7️⃣ Conclusion

Ye system ek early warning tool hai jo:

Students ko early stage me identify karta hai

Advisors ko timely action lene me madad deta hai

Simple, explainable aur transparent approach follow karta hai

Future me is system ko machine learning models ke sath aur improve kiya ja sakta hai.
