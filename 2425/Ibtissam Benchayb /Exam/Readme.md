# ETL and Streaming Pipeline with Apache Spark and Kafka

This project demonstrates the implementation of a data pipeline integrating batch and real-time (streaming) processing using Apache Spark and Kafka. The pipeline ingests, transforms, analyzes, and exports student data.

---

## Table of Contents

1. [Project Description](#project-description)
2. [Technologies Used](#technologies-used)
3. [Setup and Configuration](#setup-and-configuration)
4. [Pipeline Workflow](#pipeline-workflow)
   - [1. Data Ingestion](#1-data-ingestion)
   - [2. Data Transformation](#2-data-transformation)
   - [3. Data Analysis](#3-data-analysis)
   - [4. Data Export](#4-data-export)
5. [Challenges and Solutions](#challenges-and-solutions)
6. [Reporting and Analysis](#reporting-and-analysis)
7. [How to Run the Project](#how-to-run-the-project)

---

## Project Description

The goal of this project is to design and implement a complete ETL (Extract, Transform, Load) pipeline for processing student data from both static CSV files and real-time Kafka streams. The pipeline includes data transformations, statistical analysis, and saving the processed data for further use.

---

## Technologies Used

- **Apache Kafka**: For real-time data ingestion and streaming.
- **Apache Spark**: For data processing in both streaming and batch modes.
- **Python**: The main programming language for implementing the pipeline.
- **Pandas**: For additional data analysis.
- **Kafka-python**: Library to interact with Kafka.
- **PySpark**: Library for working with Apache Spark.

---

## Setup and Configuration

### 1. Required Tools
- Java (configured and added to the PATH)
- Apache Spark
- Apache Kafka

### 2. Environment Configuration
- **Kafka Consumer**:
  - Secure communication using SSL (ca.pem, service.cert, service.key).
  - Key parameters: `bootstrap.servers`, `group.id`, and `auto.offset.reset`.
- **Spark**:
  - Configured for real-time processing with Spark Streaming.
  - Batch processing handled with `SparkSession`.

---

## Pipeline Workflow

### 1. Data Ingestion
- **Source**: Kafka topic (`ibtissam`).
- **Format**: Structured data messages in the format:  
  `"FirstName LastName, Age, Field"`  
  Example: `"Ali Bennis, 21, Computer Science"`
- **Implementation**: 
  - Spark Streaming is used to consume real-time messages from Kafka.
  - Static CSV files are loaded using PySpark.

### 2. Data Transformation
- **Steps**:
  1. **Data Cleaning**:
     - Filter out improperly formatted messages.
     - Validate fields (e.g., ensure age is an integer).
  2. **Standardization**:
     - Convert names to uppercase.
     - Transform age values to integers.
  3. **Filtering**:
     - Select students over 20 years old.
- **Example**:  
  Input: `"Ali Bennis, 21, Computer Science"`  
  Output: `"ALI BENNIS, 21, COMPUTER SCIENCE"`

### 3. Data Analysis
- **Statistics**:
  - Calculate the average age per field.
  - Total number of students per field.
  - Distribution of ages by field (minimum, maximum, median).
- **Example Results**:
  - *Computer Science*: Average age of 22.5 years.
  - *Management*: Average age of 23.1 years.

### 4. Data Export
- **Format**: Transformed data is saved to a CSV file (`etudiants_transformed.csv`).
- **Columns**: `first_name`, `last_name`, `age`, `field`.



## Reporting and Analysis

### Summary of Steps:
1. Kafka and Spark setup for secure communication and real-time data collection.
2. Data cleaning, standardization, and statistical analysis using Spark.
3. Results exported to a CSV file for further use.

### Impact:
This pipeline is modular and extensible, allowing integration of additional data sources or new types of analysis.

---

## How to Run the Project

1. **Set Up Kafka**:
   - Start Kafka and create a topic (`ibtissam`).
   - Configure SSL certificates for secure communication.
2. **Run the Kafka Producer**:
   - Use the provided Python script to send student data to Kafka.
3. **Start the Kafka Consumer**:
   - Use Spark Streaming to consume and process the messages in real time.
4. **Execute the Batch Script**:
   - Load, transform, and analyze data from a CSV file.
5. **Export Results**:
   - Save the transformed data to `etudiants_transformed.csv`.

---

## Author

This project was completed as part of a data engineering exam. It showcases a practical understanding of data ingestion, transformation, and real-time processing with Apache Spark and Kafka.

