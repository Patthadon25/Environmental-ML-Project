# Prediction of Air Quality Index (AQI)
### การพยากรณ์ดัชนีคุณภาพอากาศ

**Project Type:** Environmental Data Science | Machine Learning | Regression Analysis

**Prepared by:** 
    1. Patthadon Maneeratana — 6631125721
    2. Pattaradanai Yoosuk — 6631128621
    3. Ratchapol Kamtaedthong — 6631134321
---

# 🇹🇭 ภาษาไทย

## 1. ชื่อโครงงาน (Project Title)

**การพยากรณ์ดัชนีคุณภาพอากาศ (Air Quality Index: AQI) ด้วยเทคนิค Machine Learning**

## 2. ปัญหาสิ่งแวดล้อม (Environmental Problem)

มลพิษทางอากาศเป็นปัญหาสิ่งแวดล้อมที่ส่งผลกระทบต่อสุขภาพของประชาชนและคุณภาพชีวิต โดยเฉพาะมลพิษจากฝุ่นละอองและก๊าซต่าง ๆ ซึ่งมีความเข้มข้นเปลี่ยนแปลงตามสภาพแวดล้อมและกิจกรรมของมนุษย์

ดัชนีคุณภาพอากาศ (Air Quality Index: AQI) เป็นตัวชี้วัดที่ใช้สื่อสารระดับคุณภาพอากาศ การพัฒนาแบบจำลอง Machine Learning เพื่อพยากรณ์ค่า AQI จากข้อมูลความเข้มข้นของมลพิษทางอากาศจึงเป็นแนวทางหนึ่งในการประยุกต์ใช้ Data Science เพื่อสนับสนุนการติดตามและประเมินคุณภาพอากาศ

## 3. แหล่งข้อมูล (Dataset Source)

- **Dataset:** Air Quality Data in India
- **Source:** Kaggle
- **Link:** https://www.kaggle.com/datasets/rohanrao/air-quality-data-in-india

ชุดข้อมูลประกอบด้วยข้อมูลความเข้มข้นของสารมลพิษทางอากาศ เช่น PM2.5, PM10, CO, NO, NO2, NOx, NH3, SO2, O3 และสารมลพิษอื่น ๆ โดยใช้ข้อมูลเหล่านี้เป็นตัวแปรในการพยากรณ์ค่า AQI

## 4. คำถามวิจัย (Research Questions)

1. ตัวแปรมลพิษทางอากาศสามารถนำมาใช้พยากรณ์ค่าดัชนีคุณภาพอากาศ (AQI) ได้อย่างมีประสิทธิภาพหรือไม่?
2. แบบจำลอง Regression ใดให้ประสิทธิภาพในการพยากรณ์ค่า AQI ได้ดีที่สุด?
3. ตัวแปรมลพิษทางอากาศชนิดใดมีอิทธิพลต่อการพยากรณ์ค่า AQI มากที่สุด?
4. ผลการวิเคราะห์ความสำคัญของตัวแปรสามารถอธิบายความสัมพันธ์ระหว่างมลพิษทางอากาศกับค่าที่แบบจำลองพยากรณ์ได้อย่างไร?

## 5. วิธีการศึกษา (Methods)

ประยุกต์ใช้เทคนิค Machine Learning ประเภท Regression เพื่อสร้างและเปรียบเทียบแบบจำลองสำหรับพยากรณ์ค่า AQI โดยประกอบด้วย 8 แบบจำลอง ได้แก่

1. Linear Regression
2. Polynomial Regression
3. Ridge Regression
4. Lasso Regression
5. Elastic Net Regression
6. K-Nearest Neighbors (KNN) Regression
7. Decision Tree Regression
8. Support Vector Regression (SVR)

กระบวนการศึกษา:
- Data Preparation and Preprocessing
- Feature Scaling
- Model Training
- Hyperparameter Tuning using GridSearchCV
- Model Evaluation using R², MAE and RMSE
- Model Interpretation using SHAP

## 6. ผลการศึกษา (Main Results)

ผลการเปรียบเทียบประสิทธิภาพของแบบจำลองมีดังนี้

| Model | R² | MAE | RMSE |
|---|---:|---:|---:|
| SVR | **0.935770** | **15.582903** | **23.117253** |
| KNN Regression | 0.931153 | 16.144849 | 23.933667 |
| Polynomial Regression | 0.929993 | 16.738860 | 24.134441 |
| Linear Regression | 0.921714 | 18.153469 | 25.521692 |
| Ridge | 0.921645 | 18.161199 | 25.532868 |
| Lasso | 0.921601 | 18.169064 | 25.540033 |
| Elastic Net | 0.921529 | 18.174527 | 25.551756 |
| Decision Tree Regression | 0.919166 | 17.650514 | 25.933744 |

## 7. แบบจำลองที่ดีที่สุด (Best Model)

**Support Vector Regression (SVR)**

SVR ให้ประสิทธิภาพการพยากรณ์ดีที่สุดเมื่อเปรียบเทียบกับแบบจำลองทั้ง 8 ชนิด โดยมีผลการประเมินดังนี้

- R² = 0.935770
- MAE = 15.582903
- RMSE = 23.117253

ผลลัพธ์แสดงให้เห็นว่าแบบจำลอง SVR สามารถอธิบายความแปรปรวนของค่า AQI ในชุดข้อมูลทดสอบได้ประมาณ 93.58%

## 8. ความสำคัญของตัวแปร (Feature Importance)

ใช้เทคนิค SHAP (SHapley Additive exPlanations) เพื่อวิเคราะห์อิทธิพลของตัวแปรที่มีต่อผลการพยากรณ์ของแบบจำลอง SVR

ผลการวิเคราะห์พบว่า **PM2.5 และ PM10 เป็นตัวแปรที่มีอิทธิพลต่อการพยากรณ์ค่า AQI มากที่สุด** โดยมีค่า Mean Absolute SHAP สูงกว่าตัวแปรอื่นอย่างชัดเจน

## 9. การตีความเชิงสิ่งแวดล้อม (Environmental Interpretation)

จากการวิเคราะห์ความสำคัญของตัวแปรด้วย SHAP พบว่า PM2.5 และ PM10 เป็นตัวแปรหลักที่มีอิทธิพลต่อการพยากรณ์ค่าดัชนีคุณภาพอากาศ (AQI) สะท้อนให้เห็นถึงบทบาทของฝุ่นละอองในการประเมินคุณภาพอากาศของชุดข้อมูลที่ศึกษา

นอกจากนี้ ผลการวิเคราะห์ SHAP Beeswarm แสดงให้เห็นว่าเมื่อตัวแปร PM2.5 และ PM10 มีค่าสูง ค่า SHAP มีแนวโน้มเป็นบวก ซึ่งส่งผลให้ค่าที่แบบจำลองพยากรณ์เพิ่มสูงขึ้น ผลดังกล่าวแสดงถึงความสัมพันธ์ระหว่างความเข้มข้นของฝุ่นละอองกับค่าดัชนีคุณภาพอากาศที่แบบจำลองเรียนรู้จากข้อมูล

---

# 🇬🇧 English Version

## 1. Project Title

**Air Quality Index (AQI) Prediction Using Machine Learning Techniques**

## 2. Environmental Problem

Air pollution is a major environmental issue that affects public health and quality of life. The concentration of atmospheric pollutants, including particulate matter and gaseous pollutants, varies depending on environmental conditions and human activities.

The Air Quality Index (AQI) is an indicator used to communicate air quality levels. Developing machine learning models to predict AQI based on pollutant concentrations provides an opportunity to apply data science techniques to support air quality assessment and monitoring.

## 3. Dataset Source

- **Dataset:** Air Quality Data in India
- **Source:** Kaggle
- **Link:** https://www.kaggle.com/datasets/rohanrao/air-quality-data-in-india

The dataset contains various air pollutant measurements, including PM2.5, PM10, CO, NO, NO2, NOx, NH3, SO2, O3, and other pollutants. These variables are used as input features to predict AQI.

## 4. Research Questions

1. Can air pollutant concentrations be used to effectively predict the Air Quality Index (AQI)?
2. Which regression model provides the best AQI prediction performance?
3. Which air pollutants have the greatest influence on AQI prediction?
4. How can feature importance analysis explain the relationship between air pollutants and model predictions?

## 5. Methods

Eight regression algorithms were implemented and compared to identify the most effective model for AQI prediction:

1. Linear Regression
2. Polynomial Regression
3. Ridge Regression
4. Lasso Regression
5. Elastic Net Regression
6. K-Nearest Neighbors (KNN) Regression
7. Decision Tree Regression
8. Support Vector Regression (SVR)

The research workflow consists of:

- Data Preparation and Preprocessing
- Feature Scaling
- Model Training
- Hyperparameter Tuning using GridSearchCV
- Model Evaluation using R², MAE, and RMSE
- Model Interpretation using SHAP

## 6. Main Results

The performance of the eight regression models was evaluated and compared.

| Model | R² | MAE | RMSE |
|---|---:|---:|---:|
| SVR | **0.935770** | **15.582903** | **23.117253** |
| KNN Regression | 0.931153 | 16.144849 | 23.933667 |
| Polynomial Regression | 0.929993 | 16.738860 | 24.134441 |
| Linear Regression | 0.921714 | 18.153469 | 25.521692 |
| Ridge | 0.921645 | 18.161199 | 25.532868 |
| Lasso | 0.921601 | 18.169064 | 25.540033 |
| Elastic Net | 0.921529 | 18.174527 | 25.551756 |
| Decision Tree Regression | 0.919166 | 17.650514 | 25.933744 |

## 7. Best Model

**Support Vector Regression (SVR)**

SVR achieved the best overall prediction performance among the eight evaluated regression models.

Performance metrics:

- R² = 0.935770
- MAE = 15.582903
- RMSE = 23.117253

The results indicate that the SVR model explains approximately 93.58% of the variance in AQI values in the test dataset.

## 8. Feature Importance

SHAP (SHapley Additive exPlanations) was applied to interpret the contribution of individual features to the SVR model predictions.

The analysis revealed that **PM2.5 and PM10 were the most influential features in predicting the Air Quality Index (AQI)**, with substantially greater mean absolute SHAP values than the other variables.

## 9. Environmental Interpretation

SHAP analysis revealed that PM2.5 and PM10 were the primary influential features in AQI prediction, highlighting the importance of particulate matter in air quality assessment within the studied dataset.

Furthermore, the SHAP Beeswarm plot indicated that higher PM2.5 and PM10 concentrations were generally associated with positive SHAP values, contributing to higher predicted AQI values. These findings demonstrate the relationship between particulate matter concentrations and AQI predictions learned by the machine learning model.

---

**Project Author:** [Your Full Name]

**Technologies:** Python | Pandas | NumPy | Scikit-learn | SHAP | Matplotlib | Seaborn

