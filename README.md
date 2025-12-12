# Set up and Track Virtual Environment
```python
# Create and Activate Python Virtual Environment (https://docs.python.org/3/library/venv.html)
virtualenv venv # just do once
sourve venv/bin/activate

pip install -r requirements.txt
pip freeze > requirements.txt
```


# Finding Dataset Bias Using Language Models

---

### 👥 **Team Members**

| Name             | GitHub Handle | Contribution                                                             |
|------------------|---------------|--------------------------------------------------------------------------|
| Grace Kim    | @gracekim247 | Data exploration, visualization, overall project coordination            |
| Caroline Klein  | @CaroAK     | Data collection, exploratory data analysis (EDA), dataset documentation  |
| Roger Nguyen     | @hiepngiyenduc2005  | Data preprocessing, feature engineering, data validation                 |
| Abrar Bari      | @abbari6566       | Model selection, hyperparameter tuning, model training and optimization  |
| Jessica-Rita Ochuba       | @jessica-rita    | Model evaluation, performance analysis, results interpretation           |
| Adena Paul      | @a-k-paul    | Model evaluation, performance analysis, results interpretation           |


---

## 🎯 **Project Highlights**

**Example:**

- Developed a BERT-based text classification model to detect biased vs. unbiased language.
- Fine-tuned a pretrained transformer model to significantly improve accuracy and F1 score over a baseline.
- Evaluated model fairness by analyzing performance across multiple bias categories.
- Tested model generalizability by applying it to the BBQ bias benchmark dataset.

---

## 👩🏽‍💻 **Setup and Installation**

This project uses a Python virtual environment and a requirements.txt file generated with pip freeze to ensure full reproducibility, including all direct and indirect dependencies.

# 1. Clone the Repository
        ```git clone https://github.com/your-repo-name.git
        cd language-bias```

# 2. Create and Activate a Virtual Environment
        Create the virtual environment (run once)
        ```python3 -m venv venv```
        
        Activate the environment
        ```source venv/bin/activate    # macOS / Linux
        venv\Scripts\activate     # Windows```

# 3. Install Dependencies
        ```pip install -r requirements.txt```
        
        The requirements.txt file includes pinned versions of all required libraries to ensure consistent results across environments.

# 4. Run the Project
        ```jupyter notebook```
        
        Open the main notebook and run all cells to reproduce the experiments and results.

# Optional: Regenerate Requirements

        If dependencies are updated or modified:
        
        ```pip freeze > requirements.txt```

# Notes

        Python 3.9+ is recommended.
                
        GPU acceleration is optional but improves training speed.
                
        If using Google Colab, dependencies can be installed directly from requirements.txt.

---

## 🏗️ **Project Overview**

**Describe:**

- This project was completed as part of the Break Through Tech AI Studio Challenge in collaboration with Meta. The objective was to design and evaluate a machine learning model capable of identifying biased language in text.
- Bias detection is a critical problem for large-scale platforms, where automated systems are often used to moderate content and support decision-making. Inaccurate or inconsistent bias detection can lead to unfair outcomes or missed harmful content. Through this project, we explored how fine-tuning large language models impacts both performance and fairness across different demographic categories.
- By evaluating the model on both in-domain data and the BBQ bias benchmark dataset, this work highlights the challenges of generalization and the importance of robust bias detection systems in real-world applications.

---

## 📊 **Data Exploration**

- Primary dataset consists of labeled text samples annotated as biased or unbiased, with associated bias categories.
- Text was tokenized using BERT’s tokenizer with truncation and padding.
- Dataset was analyzed for class balance and category distribution.
- Bias was often subtle and context-dependent, creating challenges for both labeling and modeling.
- The BBQ dataset was used as an external benchmark to evaluate how well the model generalizes to unseen domains.

**Potential visualizations to include:**

* Plots, charts, heatmaps, feature visualizations, sample dataset images

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

**You might consider describing the following (as applicable):**

- Fine-tuning significantly improved performance over the baseline model.
- Overall accuracy and F1 score increased to the low-80% range on the in-domain evaluation set.
- Performance was consistent across bias categories, with no major category-specific failures.
- Confusion matrix analysis showed a reduction in false negatives, meaning the model became better at identifying biased language.
- When evaluated on the BBQ dataset, performance decreased relative to the in-domain dataset.
- This drop is attributed to domain shift, different bias definitions, and more subtle bias cues present in BBQ.

**Potential visualizations to include:**

* Confusion matrix, precision-recall curve, feature importance plot, prediction distribution, outputs from fairness or explainability tools

---

## 🚀 **Next Steps**

- Expand from binary classification to categorical bias classification.
- Train on multiple bias datasets, including BBQ, to improve generalization.
- Explore domain adaptation or data augmentation techniques.
- Investigate explainability tools to better understand model predictions.
  
---

## 📝 **License**

If applicable, indicate how your project can be used by others by specifying and linking to an open source license type (e.g., MIT, Apache 2.0). Make sure your Challenge Advisor approves of the selected license type.

**Example:**
This project is licensed under the MIT License.

---

## 🙏 **Acknowledgements** (Optional but encouraged)

Thank your Challenge Advisor, host company representatives, TA, and others who supported your project.
