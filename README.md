[![Made withJupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange?style=for-the-badge&logo=Jupyter)](https://jupyter.org/try)


# Automatic Cardiology Report Generator with ChatGPT API

This pipeline is designed to generate automatic cardiology reports based on patient information and medical findings. It utilizes a multiple-choice system to collect essential details about the patient, such as patient ID, age, gender, blood pressure, breath sounds, heart sounds, ECG results, and echocardiogram findings. The gathered information is then processed and utilized as input for generating a detailed medical report using the ChatGPT API. The report can be emailed or added to the EHR as a medical note of a consultation.


## Instructions for Usage:

### 1. **Collect Patient Information:**
- Run the code to collect patient information, including patient ID, age, gender, blood pressure, breath sounds, heart sounds, ECG results, and echocardiogram findings.
- Follow the prompts to provide the required information. If no predefined option fits the patient findings, the possibility exists to introduce the feature manually.

### 2. **Generate Medical Report:**
- The provided patient details and medical findings will be used to generate a comprehensive medical report using the ChatGPT API.
- Ensure you have the OpenAI API credentials set up with the appropriate access rights.

### 3. **API Key Setup:**
- Replace the placeholder  with your actual OpenAI API key.
```
API_key = ""

os.environ["OPENAI_API_KEY"] = API_key

client = openai.Client()

```
-   You can see where to find your openAI API key [here](https://help.openai.com/en/articles/4936850-where-do-i-find-my-secret-api-key).

### 4. **Run the Code:**
- After setting up the API key, execute the code to generate the medical report.

### 5. **Evaluate the Quality of the Report:**
- After the report is generated, evaluate the queality of the generated text with evaluation functions. You can either use language models like Bio_ClinicalBERT, ROBERTA and chatGPT. You can also evaluate how different levels of temperature affect report generation. 

## Code Overview:

### **Data Collection:**
- Patient information, including ID, age, gender, blood pressure, breath sounds, heart sounds, ECG results, and echocardiogram findings, is collected using a multiple-choice system.

### **Quality Evaluation:**
- The collected patient details and medical findings are utilized as input to the ChatGPT API.
- The generated medical report is then evaluated for quality using a predefined scoring system.

### **ChatGPT Integration:**
- The collected patient details and medical findings, along with the quality score, are utilized as input to the ChatGPT API.

### **Output:**
- The final medical report is printed, providing a detailed summary of the patient's cardiological condition based on the input data and quality evaluation.

### **Evaluation of the Medical Report:**
- The quality of the generated medical report is assessed using specialized Natural Language Processing models and predefined scoring systems. Three evaluation functions are employed, each utilizing different models to ensure comprehensive assessment:
    1. **BertForSequenceClassification Model:**
        - Tokenizes the medical report and predicts the quality score using the 'Bio_ClinicalBERT' model.
    2. **XLM-Roberta Model:**
        - Tokenizes the medical report and predicts the quality score using the 'xlm-roberta-base' model.
    3. **ChatGPT Evaluation:**
        - Uses the ChatGPT API to assess the quality of the medical report and assigns a quality score.
      
### Notebook
In this link you will find the [notebook](Automatic_report.ipynb).

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

## Important Notes:

- Ensure accurate input to receive a meaningful medical report.
- Review and validate the generated report before sharing it with relevant stakeholders.
- Please exercise caution when dealing with sensitive patient information and ensure compliance with data privacy regulations and ethical guidelines.
