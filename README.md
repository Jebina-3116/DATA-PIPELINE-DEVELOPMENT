# DATA-PIPELINE-DEVELOPMENT

COMPANY:CODTECH IT SOLUTIONS

NAME:JEBINA SELIN S.D

INTERN ID:CT04DG3456

DOMAIN:DATA SCIENCE

DURATION:4 WEEKS

MENTOR:NEELA SANTOSH

Objective of the Project:
The goal of this project is to implement a complete ETL (Extract, Transform, Load) pipeline using Python that simulates a real-world data preprocessing workflow. The pipeline reads raw data from a CSV file, cleans and transforms it using appropriate preprocessing techniques, and finally saves the processed data to a new CSV file. To ensure robustness and traceability, logging is integrated into every step of the process. The project also includes the creation of a sample dataset for testing and demonstration purposes.

 Technologies and Libraries Used:
Python: Main programming language for scripting the ETL logic.

Pandas: Used for data manipulation and reading/writing CSV files.

NumPy: For numerical operations and generating synthetic data.

Scikit-learn: Provides tools like SimpleImputer, StandardScaler, OneHotEncoder, Pipeline, and ColumnTransformer for data transformation.

Logging: The built-in Python logging module is used for real-time monitoring and debugging, particularly useful when running code in environments like Google Colab.

 Pipeline Stages:
1. Logging Setup
To ensure that messages are correctly displayed in Google Colab or Jupyter notebooks, the logging system is configured to use a StreamHandler that prints messages to the console. Logging helps trace data flow, monitor errors, and debug issues during each stage of the ETL process. Handlers are cleared before reinitializing to avoid duplicate logs, which is a common problem in notebook environments.

2. Extract Stage – extract_data(file_path)
This function reads data from a given CSV file path using pandas.read_csv(). It logs the operation and the shape of the dataset. If the file is not found or cannot be read, it catches the exception and logs an error. This stage simulates the data ingestion step in real-world pipelines.

3. Transform Stage – transform_data(data)
The core of the pipeline lies in this step. The function performs the following:

Separation of Columns: Columns are divided into numeric and categorical types based on data types.

Numeric Transformation: Missing values are filled using the mean, and data is standardized using StandardScaler for consistent scaling.

Categorical Transformation: Missing values are imputed with the most frequent value, and the data is encoded using OneHotEncoder, which is robust to unknown categories.

These transformations are combined using a ColumnTransformer and applied via a Pipeline. The output is converted to a DataFrame using toarray() if needed and returned for loading.

4. Load Stage – load_data(cleaned_data, output_path)
This function saves the transformed DataFrame to a CSV file using to_csv(). It logs a success message or captures and logs an error if the saving fails. This simulates storing cleaned data into a target location like a database or a cloud storage bucket in enterprise systems.

 Testing: Dummy Data Generator – create_sample_csv()
To demonstrate the ETL pipeline without needing an external dataset, a synthetic dataset is generated using NumPy:

Numeric Columns: Three numeric columns are created using random values and normal distribution. About 5% of values are randomly set to NaN to simulate real-world missing data scenarios.

Categorical Columns: Two columns are created using random selections from a fixed set of categories. One of the columns includes None values to test the imputation process.

This sample dataset is saved as sample_data.csv and serves as input for the ETL pipeline.

▶ Pipeline Execution:
The pipeline is executed in the following sequence:

python
Copy
Edit
create_sample_csv()   # Creates sample raw data
run_pipeline()        # Executes extract, transform, and load stages
At the end, the cleaned data is saved as cleaned_data.csv and can be previewed using pandas.read_csv().

 Key Benefits of This ETL Pipeline:
Modularity: Each phase of the pipeline (Extract, Transform, Load) is implemented as a separate function, improving reusability and readability.

Scalability: Can be easily extended to work with real-world datasets and integrate with APIs or databases.

Real-Time Logging: Logging allows tracking data flow and errors, making debugging easier during development and deployment.

Colab-Compatible: Designed to avoid duplicated logging output in Colab, which improves user experience in notebook environments.

Data Quality Handling: Addresses common preprocessing tasks like handling missing values and categorical encoding, making the data model-ready.

 Files Created:
sample_data.csv: Input data with missing values and mixed column types.

cleaned_data.csv: Output file after transformation, ready for model training or analysis.

 Conclusion:
This project demonstrates a practical, beginner-friendly ETL pipeline implementation in Python. It simulates the core stages of a data engineering workflow, with added logging for clarity. The use of Scikit-learn’s preprocessing utilities shows how machine learning-ready data can be prepared from raw CSV files. This pipeline can serve as a foundation for more advanced data science and machine learning projects, where data cleaning is a critical first step.

OUTPUT:

<img width="863" height="733" alt="Image" src="https://github.com/user-attachments/assets/bafd26e4-200b-4ae2-b353-2fb45758ae58" />
<img width="785" height="282" alt="Image" src="https://github.com/user-attachments/assets/8bf234da-0f15-477b-a44c-ef0f837a1989" />







