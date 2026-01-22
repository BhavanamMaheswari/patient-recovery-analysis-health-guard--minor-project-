# COVID-19 Patient Recovery Analysis

## Project Overview
This project analyzes COVID-19 patient data to predict recovery times based on demographic and infection-related factors. Using machine learning regression techniques, the analysis examines patterns in patient recovery across different regions, age groups, and infection sources.

## Dataset
- **File**: `patient.csv`
- **Records**: 4,213 patient cases
- **Key Columns**:
  - `id`: Patient identifier
  - `sex`: Gender (male/female)
  - `birth_year`: Year of birth (used to calculate age)
  - `country`: Country of patient
  - `region`: Geographic region
  - `infection_reason`: Primary source of infection
  - `infection_order`: Generation of infection (1st, 2nd, etc.)
  - `infected_by`: ID of patient who infected this patient
  - `contact_number`: Number of people contacted
  - `confirmed_date`: Date of COVID-19 confirmation
  - `released_date`: Date patient was released/recovered
  - `deceased_date`: Date of death (if applicable)
  - `state`: Current status (released, isolated, deceased)

## Project Structure

### 1. **Data Loading**
   - Load patient data from CSV file
   - Display initial dataset preview

### 2. **Data Preprocessing & Feature Engineering**
   - **Age Calculation**: Derive age from birth_year (base year: 2026)
   - **Date Conversion**: Convert date columns to datetime objects
   - **Target Variable**: Calculate `recovery_days` as days between confirmed date and release date
   - **Data Cleaning**: Remove records with invalid recovery durations

### 3. **Exploratory Data Analysis (EDA)**
   - **Gender Distribution**: Analyze infection spread by gender
   - **Age Distribution**: Visualize patient age demographics
   - **Regional Analysis**: Identify most impacted regions
   - **Infection Sources**: Examine primary routes of infection transmission
   - **Correlation Analysis**: Identify relationships between recovery factors

### 4. **Outlier Detection**
   - Use IQR (Interquartile Range) method to detect anomalies
   - Visualize outliers using boxplots
   - Clean data by removing extreme values for better model performance

### 5. **Linear Regression Model**
   - **Features Used**:
     - `age`: Patient's age
     - `contact_number`: Number of contacts
     - `infection_order`: Infection generation order
   - **Target Variable**: `recovery_days`
   - **Train-Test Split**: 80-20 ratio
   - **Model Evaluation**: R² score and residual analysis

### 6. **Prediction**
   - Test the model with sample patient data
   - Predict recovery time in days

## Requirements
```
pandas
numpy
matplotlib
seaborn
scikit-learn
```

## Usage
1. Ensure `patient.csv` is in the same directory as the notebook
2. Open `Covid_19.ipynb` in Jupyter Notebook or VS Code
3. Run cells sequentially to:
   - Load and preprocess data
   - Generate visualizations and analyses
   - Train the regression model
   - Make predictions on new cases

## Key Findings
The analysis explores relationships between patient demographics, infection patterns, and recovery duration. The linear regression model helps predict recovery time based on key patient characteristics.

## Model Performance
The regression model is evaluated using:
- **R² Score**: Measures goodness of fit
- **Mean Squared Error (MSE)**: Quantifies prediction error magnitude
- **Residual Analysis**: Visualizes prediction errors

## Example Prediction
For a 45-year-old patient with 10 contacts and infection order of 1:
- **Predicted Recovery Time**: ~X days (varies based on model training)

## Future Improvements
- Include additional features (comorbidities, treatment type)
- Experiment with advanced models (Random Forest, Gradient Boosting)
- Cross-validation for more robust evaluation
- Time-series analysis of infection spread patterns
- Geographic heat mapping of outbreaks

## Author
Created as a mini-project for COVID-19 data analysis and machine learning

## License
Dataset source: Publicly available COVID-19 patient data
