# Machine-Learning-Based-Sonic-Log-Prediction-Using-Multi-Well-Data
This project was developed as part of the Geophysical Data Analysis practicum. After understanding and analyzing existing well log processing codes, the workflow was redesigned and optimized based on personal comprehension, demonstrating a complete pipeline for multi-well LAS analysis and machine learning–based sonic log prediction.

## Purpose of This Project
This project aims to:

- Understand the characteristics of well log data
- Apply quality control (QC) to multi-well LAS datasets
- Perform exploratory data analysis (EDA)
- Implement a proper machine learning pipeline without data leakage
- Predict sonic logs (DT) from conventional well logs
- Serve as an educational reference for geophysical data analysis and machine learning

---

## Theoretical Background

### 1️⃣ Well Logging Concept
Well logs represent continuous measurements of subsurface physical properties along depth. Common logs used in this project include:

- **GR (Gamma Ray):** indicator of shale content  
- **RHOB (Bulk Density):** rock density information  
- **NPHI (Neutron Porosity):** porosity-related measurement  
- **RT (Resistivity):** fluid and saturation indicator  
- **PEF (Photoelectric Factor):** lithology discrimination  
- **CALI (Caliper):** borehole condition  
- **DT (Sonic Log):** elastic property related to porosity and lithology  

Sonic logs are often missing or incomplete in real datasets, motivating predictive approaches.

---

### 2️⃣ Machine Learning for Well Logs
Machine learning regression models learn relationships between multiple input logs and a target log (DT) without explicitly defining physical equations.  
This project uses **Random Forest Regression** because it:

- Handles nonlinear relationships
- Is robust to noise and outliers
- Performs well on tabular geoscience data

---

### 3️⃣ Cross-Well Validation
Instead of splitting data by depth, data are split **by well**:

- Training wells and testing wells are different
- Prevents data leakage
- Better represents real-world prediction scenarios

---

## Dataset Description

### 🔹 Synthetic LAS Data
This repository uses **synthetic LAS data** generated to resemble realistic well log distributions.

**Why synthetic data are used:**
- Avoids confidentiality issues with real field data
- Enables full reproducibility
- Suitable for educational and practicum purposes
- Allows controlled testing of the workflow

⚠️ **Important:**  
Synthetic data do not represent real reservoir conditions and should not be used for engineering or operational decisions.

---

## Workflow Explanation (Step-by-Step)

### 1️⃣ Load Libraries
Python libraries are imported for numerical computation, visualization, LAS file handling, and machine learning.

---

### 2️⃣ Load and Quality Control LAS Files
- All LAS files in the working directory are automatically detected
- Only wells with complete required logs are used
- Wells with missing logs are excluded to maintain data quality

---

### 3️⃣ Well Log Visualization
Each log is plotted against depth to:
- Understand vertical trends
- Detect abnormal responses
- Support geophysical interpretation

---

### 4️⃣ Exploratory Data Analysis (EDA)
EDA includes:
- Histograms to inspect data distributions
- Boxplots to identify outliers
- Correlation heatmaps to evaluate relationships between logs

---

### 5️⃣ Outlier Handling
Outliers are removed using the **Interquartile Range (IQR)** method to reduce the influence of extreme values on model training.

---

### 6️⃣ Data Normalization
Min–Max normalization is applied:
- Fitted only on training data
- Prevents information leakage
- Improves machine learning stability

---

### 7️⃣ Machine Learning Model
A **Random Forest Regressor** is trained using:
- Input logs: GR, RHOB, NPHI, RT, PEF, CALI
- Target log: DT

---

### 8️⃣ Model Evaluation
Model performance is evaluated using:
- **R² score**
- **Root Mean Square Error (RMSE)**
- Scatter plot of actual vs predicted DT

---

### 9️⃣ Final Prediction Visualization
Predicted DT values are plotted against depth and compared with actual DT to visually assess prediction quality.

---

## Output
The workflow produces:
- Well log visualizations
- EDA plots
- Correlation heatmaps
- Prediction performance metrics
- Final DT prediction curves

---

## Limitations
- Uses synthetic data
- Limited number of wells
- No geological zoning or facies modeling
- No uncertainty quantification
- Not yet validated with real field data

---

## Future Development & Professional Use
This workflow **has the potential to be developed for professional applications**, but requires:

- Validation using real field data
- Geological and petrophysical expert review
- Feature engineering (e.g., Vshale, porosity models)
- Advanced models (XGBoost, Neural Networks)
- Uncertainty and sensitivity analysis

---

## Educational Disclaimer
> This project is currently intended for educational purposes. Any professional or industrial application requires further development, validation, and expert verification.

---

## Feedback and Contact
If you have **criticisms, suggestions, or any feedback** that could help improve this program, please feel free to contact:

📧 **ilhamazhar1308@gmail.com**

All constructive feedback is highly appreciated for future development.

---

## Technologies Used
- Python  
- NumPy, Pandas  
- Matplotlib, Seaborn  
- Scikit-learn  
- Lasio  

---

## Author

**Ilham Azhar**  
Geophysical Engineering  
Sumatera Institute of Technology (ITERA)

---

## Acknowledgment
This work was developed as part of academic learning in geophysical data analysis and is inspired by standard practices in geoscience and machine learning.

