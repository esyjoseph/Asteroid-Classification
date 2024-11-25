# **Classifying Potentially Hazardous Near-Earth Objects: A Machine Learning Approach to Planetary Defense**

**SOFT SKILL NOTE:**
Although astronomy isn't my area of expertise—my background lies in Economics, Business Development, and Sales Systems—this project was a chance to showcase my ability to learn quickly and solve problems outside my comfort zone. It highlights my capacity to think critically, dive deep into data for meaningful insights, and adapt through iterative learning. By selecting relevant features, addressing imbalanced datasets, and refining models based on performance feedback, I demonstrated not only technical skills but also essential soft skills like effective communication and collaboration, especially when consulting with domain experts. This experience reinforced my ability to independently learn and adapt, ensuring that complex concepts are translated into clear, actionable outcomes. 

**Introduction**
Planetary defense is a critical area focused on protecting Earth from potential asteroid impacts. With the increasing detection of Near-Earth Objects (NEOs), accurately identifying those that pose a significant threat is paramount. This project aims to enhance planetary defense mechanisms by developing a machine learning model to classify Potentially Hazardous Asteroids (PHAs). Leveraging data from NASA’s WISE/NEOWISE mission and the JPL Small-Body Database, the project achieves high accuracy and recall in classifying PHAs, demonstrating the potential to optimize resource allocation and prioritize observation efforts effectively.

**Stakeholders:
** The primary stakeholders include space agencies like NASA, planetary defense teams, and governmental bodies responsible for disaster preparedness. Their motivation lies in early detection and accurate classification of hazardous asteroids to prevent catastrophic events and efficiently allocate observational resources.

**Business Objectives**
This project aims to contribute to a safer planet by accurately classifying Potentially Hazardous Asteroids (PHAs). The key objectives include:
- Enhance Planetary Defense: Early identification of hazardous asteroids empowers authorities to take timely action, potentially preventing catastrophic events.
- Optimize Resource Allocation: With vast amounts of Near-Earth Object (NEO) data available, this model helps prioritize observation and analysis efforts, ensuring focus on the most significant threats.
- Facilitate Specialized Team Focus: By efficiently filtering and identifying high-risk asteroids, the model frees up specialized teams to concentrate on trajectory simulations and uncertainty assessments, improving the overall responsiveness of planetary defense mechanisms.

**Project Overview**
This project delves into the realm of Near-Earth Objects (NEOs) with the goal of classifying which ones are potentially hazardous to Earth. The project encompasses the following phases:
- Data Visualization: Visualizing the relationships between orbital characteristics helped uncover patterns and challenges in detecting NEOs.
- Machine Learning: Trained and evaluated various machine learning models to classify NEOs, prioritizing those capable of handling non-linearity and imbalanced data.
- Model Refinement: Improved the models using hyperparameter tuning and tested them on a larger dataset.
- Deployment: Deployed the best-performing model using Streamlit, creating an interactive web application for classifying NEO hazards.
This project showcases ability to analyze data, learn independently, select relevant features, handle imbalanced datasets, and communicate technical findings clearly.

**Data Collection**
Source: NASA's Center for Near-Earth Object Studies (CNEOS)
- Dataset 1: Wide-field Infrared Survey Explorer (WISE)
  Entries: 398 asteroid observations
- Dataset 2: JPL Small-Body Database
  Entries: 36,750 NEOs

**Attributes:**
Both datasets contain attributes related to the physical and orbital characteristics of NEOs, including:
Designation: Identifier name
Discovery Date: Date of discovery
H (mag): Absolute magnitude (brightness)
MOID (au): Minimum Orbit Intersection Distance
q (au): Perihelion distance
Q (au): Aphelion distance
Period (yr): Orbital period
i (deg): Orbital inclination
PHA: Binary classification label (Potentially Hazardous or not)
Orbit Class: Classification based on orbital characteristics

**Features**
Key features used for classification include:
Designation: Identifier name
Discovery Date: Date of discovery
H (mag): Absolute magnitude (brightness)
MOID (au): Minimum Orbit Intersection Distance
q (au): Perihelion distance
Q (au): Aphelion distance
Period (yr): Orbital period
i (deg): Orbital inclination
PHA: Binary classification label (Potentially Hazardous or not)
Orbit Class: Classification based on orbital characteristics

**Exploratory Data Analysis (EDA)**
- Univariate and Multivariate Analysis: Conducted to understand the distribution and relationships between features.
- Visualizations: Created using Matplotlib and Seaborn to identify patterns and outliers in the data.
- Outlier Analysis: Assessed the impact of outliers on model performance and data integrity.

**Machine Learning Models**
Various models were trained and evaluated, including:
- LightGBM: Efficient gradient boosting framework that handles non-linearity and class imbalance effectively.
- Random Forest: Robust against overfitting, handles outliers well, and provides feature importance insights.
Emphasis:
 Handling imbalanced datasets and minimizing false negatives were prioritized to ensure the accurate classification of hazardous asteroids.

**Model Evaluation and Selection**
- Evaluation Metrics: Accuracy, Precision, Recall, and F1-Score were used to assess model performance.
- Cross-Validation: 10-fold cross-validation ensured model generalizability.
- Model Selection: The best-performing model was selected based on a combination of metrics and business objectives, prioritizing recall to minimize false negatives.

**SHAP Analysis**
SHAP (Shapley Additive ExPlanations):
Conducted to interpret model predictions and understand feature importance.

Key Insights:
- H (mag): Highest influence; higher values (dimmer objects) increase the likelihood of a PHA classification.
- MOID (au): Second most influential; smaller values (closer proximity to Earth) significantly elevate PHA classification probability.
- Other Features: q (au), Q (au), and i (deg) contribute marginally to the model’s predictions.
This analysis aligns with domain knowledge, reinforcing the model’s validity and interpretability.

**Misclassification Analysis**
Detailed analysis of consistently misclassified asteroids revealed:
- Patterns: Dim, small asteroids with high H (mag) and very small MOID (au) were predominantly misclassified.
- Insights: These objects are challenging to detect and underrepresented in datasets, posing inherent difficulties in accurate classification.

**Deployment**
Asteroid & Comet Hazardousness Classifier
An interactive web application developed using Streamlit to make the model accessible to stakeholders.

Features:
  - User Inputs: Allows users to input asteroid characteristics.
  - Instant Classification: Provides immediate classification results indicating whether an asteroid is hazardous.

Deployment Steps:
- Model Persistence: Saved the trained LightGBM model using joblib.
- Web Application: Built the Streamlit app with input fields for key features and integrated prediction functionality.
- Accessibility: Deployed the app locally using localtunnel to provide a public URL for stakeholder access.

**License**
This project is licensed under the MIT License.

**References**
NASA CNEOS - NEO Groups
NASA CNEOS - Near-Earth Object Discovery
NASA NEOWISE Mission
NASA Planetary Defense - NEOWISE
NASA JPL - NEO Basics
NASA Solar System Exploration - Asteroids
NASA NEO Surveyor Mission

**Contact**
Questions, especially feedback are highly encouraged, please contact me at theestherjoseph@gmail.com. 


**RESULT OF MODEL CHOSEN:**
<h3>RESULT OF MODEL CHOSEN: LightGBM - Classification Report (Trained on Larger Data)</h3>

<table>
  <tr>
    <th>Class</th>
    <th>Precision</th>
    <th>Recall</th>
    <th>F1-Score</th>
    <th>Support</th>
  </tr>
  <tr>
    <td>0</td>
    <td>1.00</td>
    <td>1.00</td>
    <td>1.00</td>
    <td>10163</td>
  </tr>
  <tr>
    <td>1</td>
    <td>0.99</td>
    <td>0.98</td>
    <td>0.98</td>
    <td>792</td>
  </tr>
  <tr>
    <td colspan="4">Accuracy</td>
    <td>1.00</td>
  </tr>
  <tr>
    <td colspan="4">Macro avg</td>
    <td>0.99</td>
  </tr>
  <tr>
    <td colspan="4">Weighted avg</td>
    <td>1.00</td>
  </tr>
</table>

<h4>LightGBM - Confusion Matrix (Trained on Larger Data)</h4>
<p>[[10156, 7], [17, 775]]</p>

