# Atelier 2 - API Development and Cloud Integration

This repository contains the deliverables for **Atelier 2** of the **BI & Data Analytics module**. The focus of this workshop was on **API development using Flask** and **Cloud Integration with Azure**. Below is a detailed overview of the contents and purpose of each file in this repository.

## Repository Structure

### 1. **API Development**
- **`api_app/`**
  - A folder containing the Flask API application.
  - Includes:
    - Python scripts for API development.
    - Simulation of e-commerce data with new data generated every second.
  - **Note:** The API currently simulates local data processing as the Azure for Students subscription has expired.

### 2. **Presentation**
- **`presentation_atelier2.pptx`**
  - A PowerPoint presentation covering:
    - Objectives of the workshop.
    - Choice of technologies and architecture.

### 3. **Azure Architecture Documentation**
- **`azure_architecture.docx`**
  - A Word document detailing:
    - The design and architecture of the Azure solution.
    - Configuration steps for Azure Event Hubs, Stream Analytics, and SQL Database.
    - Challenges faced due to the expiration of Azure for Students subscription.

## Instructions for Use

### Prerequisites
1. **Environment Setup**
   - Install [Python 3.x](https://www.python.org/downloads/) and the necessary dependencies listed in `requirements.txt`.
   - Set up a virtual environment using `venv`.
     ```bash
     python -m venv venv
     source venv/bin/activate  # For Linux/MacOS
     venv\Scripts\activate  # For Windows
     ```
   - Install dependencies:
     ```bash
     pip install -r requirements.txt
     ```
2. **API Execution**
   - Navigate to the `api_app/` .
   - Run the Flask application:
     ```bash
     python app.py
     ```
   - The API will start locally on `http://127.0.0.1:5000/`.

### Demo Simulation
- The API simulates incoming e-commerce data every second.
- You can test the API endpoints using tools like [Postman](https://www.postman.com/) or [cURL](https://curl.se/).

### Azure Architecture (For Reference)
1. **Event Hubs:**
   - Originally set up to stream e-commerce data.
2. **Stream Analytics:**
   - Used for real-time processing and aggregations.
3. **SQL Database:**
   - Final output destination for processed data.
4. **Key Challenge:**
   - Azure for Students subscription expired, limiting the current setup to local simulations.

## Summary
Atelier 2 provided practical exposure to:
- Developing APIs with Flask for real-time data simulation.
- Designing and documenting a cloud-based architecture for data streaming and processing.
- Understanding the challenges of transitioning from local to cloud environments.

For any questions or further collaboration, feel free to raise an issue in this repository or contact me directly.

---
