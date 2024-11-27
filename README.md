
# Proposed AI Platform:

This repository contains the source code and documentation for the development of an AI-based platform. The platform integrates structured and unstructured data, provides REST APIs, supports predictive modeling, and includes a natural language processing (NLP) interface for dynamic data querying.

I. Architecture
The AI Platform architecture is designed for scalability, security, and flexibility, leveraging AWS and open-source tools. Below is an overview of the architecture components:

1. Data Layer
Data Sources:

Structured Data: Stored in SQLite, including SOD and NCUA datasets.

Unstructured Data: EPA Air Quality data and additional documents stored in AWS S3.

Processing:AWS EMR with Apache Spark is used for preprocessing and normalization of datasets.

Census Tract and CERT master keys ensure accurate relationships across datasets.

2. Backend API Layer
   
Serverless Computing:APIs are built using Flask and can be deployed serverlessly on AWS Lambda.

Endpoints:API Gateway manages endpoints for data retrieval, dynamic querying, machine learning predictions, and NLP-based querying.

Caching:Temporary results are cached in AWS S3 to reduce database load and improve performance.

3. Machine Learning Layer
   
Prediction Model:A regression model is trained using historical EPA data and branch density metrics to predict PM2.5 levels.

Deployment:Models are deployed on AWS SageMaker for scalability and real-time inference.

4. NLP Interface
   
Query Parsing:Natural language queries are processed using spaCy and LangChain to extract entities and conditions.

SQL Generation:Parsed queries are dynamically converted to SQL for database interaction.

5. Security Framework
    
Authentication: User authentication is managed using Amazon Cognito.

Access Control: AWS IAM roles ensure secure access to resources.

6. Analytics Layer:

Employ Amazon Athena for query execution across structured and unstructured datasets.
Use Amazon QuickSight for data visualization.
Large Language Models (LLM) Integration:
Utilize a pre-trained LLM, such as OpenAI GPT, hosted on AWS (via API or custom SageMaker endpoint) for NLP tasks.


II. Data Integration:

  - Combines EPA, SOD, and NCUA datasets using SQLite.
    
  - Ensures normalization and consistency with Census Tract and CERT master keys.
  
- REST APIs:
  - Aggregates data for branch density and air quality categorization.
    
  - Supports dynamic user-defined queries.
    
  - Predicts PM2.5 air quality levels using machine learning.
    
  - Interprets natural language queries and generates SQL dynamically.

- Visualization:
  
  - Generates scatterplots and density maps for insights into air quality and branch density correlations.
    

### Prerequisites
- Python 3.7 or later
  
- SQLite3
  
- AWS Account (for optional cloud deployment)
  
- Libraries listed in `requirements.txt`


## Technologies Used

- Backend: Python (Flask)
  
- Database: SQLite
  
- Machine Learning: scikit-learn
  
- NLP: spaCy, LangChain
  
- Visualization: Matplotlib, Seaborn
  
- Cloud: AWS 
