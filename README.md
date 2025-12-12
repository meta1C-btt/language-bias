# Finding Dataset Bias Using Language Models

---

### 👥 **Team Members**

| Name             | GitHub Handle | Contribution                                                             |
|------------------|---------------|--------------------------------------------------------------------------|
| Grace Kim    | @gracekim247 | Data preprocessing, exploratory data analysis (EDA), visualization, project coordination            |
| Caroline Klein  | @CaroAK     | Data collection, data preprocessing, exploratory data analysis (EDA), hyperparameter tuning  |
| Roger Nguyen     | @hiepngiyenduc2005  | Data preprocessing, feature engineering, model training, data validation, external dataset testing (CrowS-Pairs)                 |
| Abrar Bari      | @abbari6566       | Model training, model optimization, performance evaluation, results interpretation  |
| Jessica-Rita Ochuba       | @jessica-rita    | Model evaluation, performance analysis, visualization, hyperparameter tuning          |
| Adena Paul      | @a-k-paul    | Model evaluation, performance analysis, results interpretation, visualization           |


---

## 🎯 **Project Highlights**

**Example:**

- Developed a BERT-based text classification model to detect biased vs. unbiased language.
- Fine-tuned a pretrained transformer model to significantly improve accuracy and F1 score over a baseline.
- Evaluated model fairness by analyzing performance across multiple bias categories.
- Tested model generalizability using the CrowS-Pairs bias benchmark dataset.

---

## 👩🏽‍💻 **Setup and Installation**

This project uses a Python virtual environment and a requirements.txt file generated with pip freeze to ensure full reproducibility, including all direct and indirect dependencies.

#### 1. Clone the Repository
        git clone https://github.com/meta1C-btt/language-bias.git
        cd language-bias

#### 2. Create and Activate a Virtual Environment
 Create the virtual environment (run once)
        python3 -m venv venv
        
Activate the environment
        source venv/bin/activate    # macOS / Linux
        venv\Scripts\activate     # Windows

#### 3. Install Dependencies
        pip install -r requirements.txt
        
The requirements.txt file includes pinned versions of all required libraries to ensure consistent results across environments.

#### 4. Run the Project
        jupyter notebook
        
Open the main notebook and run all cells to reproduce the experiments and results.

#### Optional: Regenerate Requirements

If dependencies are updated or modified:
        
        pip freeze > requirements.txt

#### Notes

Python 3.9+ is recommended.
                
GPU acceleration is optional but improves training speed.
                
If using Google Colab, dependencies can be installed directly from requirements.txt.

---

## 🏗️ **Project Overview**

- This project was completed as part of the Break Through Tech AI Studio Challenge in collaboration with Meta. The objective was to design and evaluate a machine learning model capable of identifying biased language in text.
- Bias detection is a critical problem for large-scale platforms, where automated systems are used to moderate content and support decision-making. Inaccurate or inconsistent bias detection can lead to unfair outcomes or missed harmful content. Through this project, we explored how fine-tuning large language models impacts both performance and fairness across different demographic categories.
- By evaluating the model on both in-domain data and the CrowS-Pairs bias benchmark dataset, this work highlights the challenges of generalization and the importance of robust bias detection systems in real-world applications.
---

## 📊 **Data Exploration**

- Primary dataset consists of labeled text samples annotated as biased or unbiased, with associated bias categories.
- Text was tokenized using BERT’s tokenizer with truncation and padding.
- Dataset was analyzed for class balance and category distribution.
- Bias was often subtle and context-dependent, creating challenges for both labeling and modeling.
- The CrowS-Pairs dataset was used as an external benchmark to evaluate how well the model generalizes to unseen domains.

* <img width="790" height="490" alt="image" src="https://github.com/user-attachments/assets/e2178885-4f5b-448a-bcfe-6ef9a80d40ed" />
<img width="790" height="490" alt="image" src="https://github.com/user-attachments/assets/8940dd1a-e2b4-4fab-b058-eaee4b3a406b" />
<img width="789" height="490" alt="image" src="https://github.com/user-attachments/assets/cbc0a97b-822a-4ce3-b733-e4fbd35ab556" />
<img width="790" height="490" alt="image" src="https://github.com/user-attachments/assets/cbdca38d-130c-4761-8a55-287644cb6cf9" />
<img width="789" height="490" alt="image" src="https://github.com/user-attachments/assets/638a168b-7ffb-4a17-a3e0-e1992f38b973" />

---

## 🧠 **Model Development**

- Model: BertForSequenceClassification (bert-base-uncased)
- Task: Binary text classification (biased vs. unbiased)
- Baseline: Pretrained BERT without fine-tuning
- Fine-tuning setup:
    - Learning rate: 2e-5
    - Epochs: 3
    - Batch size: 16
- Evaluation metrics:
    - Accuracy
    - Precision, Recall
    - F1 Score
- Performance was also evaluated per bias category to assess fairness and robustness.

---

## 📈 **Results & Key Findings**

- Fine-tuning significantly improved performance over the baseline model.
- Overall accuracy and F1 score increased to the low-80% range on the in-domain evaluation set.
- Performance was consistent across bias categories, with no major category-specific failures.
- Confusion matrix analysis showed a reduction in false negatives, meaning the model became better at identifying biased language.
- When evaluated on the CrowS-Pairs dataset, performance decreased relative to the in-domain dataset.
- This drop is attributed to domain shift, different bias definitions, and more subtle bias cues present in CrowS-Pairs.

**Potential visualizations to include:**

### Fine-Tuned Model
<img width="1189" height="590" alt="image" src="https://github.com/user-attachments/assets/df7aba54-2ffb-47a8-b53a-2d1ab24f4489" />
<img width="1174" height="490" alt="image" src="https://github.com/user-attachments/assets/4be94e7f-fafa-42c6-afb6-6eda87fe33e8" />

### CrowS-Pairs
<img width="507" height="455" alt="image" src="https://github.com/user-attachments/assets/1da49a0e-ce37-45b6-a1ce-f46625835479" />
<img width="1189" height="590" alt="image" src="https://github.com/user-attachments/assets/6e2e6b9e-35c2-4cd8-8453-44f4fb0b2f9d" />

---

## 🚀 **Next Steps**

- Expand from binary classification to categorical bias classification.
- Train on multiple bias datasets, including CrowS-Pairs and BBQ, to improve generalization.
- Explore domain adaptation or data augmentation techniques.
- Investigate explainability tools to better understand model predictions.
  
---

## 📝 **License**

If applicable, indicate how your project can be used by others by specifying and linking to an open source license type (e.g., MIT, Apache 2.0). Make sure your Challenge Advisor approves of the selected license type.

**Example:**
This project is licensed under the MIT License.

---

## 🙏 **Acknowledgements** 

Thank you to our Challenge Advisors and Coaches for all of their support throughout our project.
