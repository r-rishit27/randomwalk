# README: Name-Enitity Relationship Extraction In Image Using OCR, Meta LLaMA 3.1 70B, and Groq for Fast LBU-Based Inferencing

## Project Overview
This project aims to extract relationships between class and groups in our case between human glands and the hormones they secrete from images we can fine-tune our prompt for any other general use also which makes it adaptable. We use **Optical Character Recognition (OCR)** for extracting text from images and the **Meta LLaMA 3.1 70B** language model to identify the relationships between glands and hormones. To optimize processing time, we leverage **Groq's LBU-based (Latency-Bound Unit) system** for fast model inferencing. The final goal is to produce a structured **JSON** output that lists glands as keys and their respective hormones as values.

## Approach

### 1. OCR (Optical Character Recognition)
We employ **EasyOCR** to extract text from images. Here's how the process works:

- **Initialization**: The EasyOCR reader is initialized to recognize English text in the images.
- **Text Extraction**: EasyOCR processes the image to detect and extract all readable text.
- **Text Consolidation**: All extracted text fragments are combined into a single string for further processing.

### 2. Extracting Gland-Hormone Relationships with Meta LLaMA 3.1 70B
After extracting the text, we need to find the relationships between glands and the hormones they secrete. To achieve this, we use the **Meta LLaMA 3.1 70B** model, a powerful **large language model (LLM)**, to interpret the text and extract these relationships. Here’s the process:

- **Using LangChain**: We connect to the Meta LLaMA model using **LangChain**, a framework designed to interface with large models and manage their interactions.
- **Groq for Fast Inferencing**: For efficient processing, we utilize **Groq's LBU-based inferencing** system. Groq’s **LBU (Latency-Bound Unit)** allows the model to process input quickly, delivering results in significantly less time than traditional inferencing methods.
- **Prompt Design**: A prompt is carefully designed to guide the Meta LLaMA model to extract gland-hormone relationships it can fine tuned for any other genral usecase and format the result into structured **JSON**. This ensures that the model understands the task and provides the necessary information in the correct format.
- **Generating Output**: The model's output is processed and formatted into a JSON structure, where glands are the keys, and the corresponding hormones are the values.

### 3. JSON Output
The final output is a well-organized **JSON** structure that maps glands to the hormones they secrete. The format is as follows:

```json
{
    "Hypothalamus": ["TRH", "CRH", "GHRH", "Melatonin", "Dopamine", "Somatostatin"],
    "Pineal gland": ["Melatonin"],
    "Pituitary gland": ["Vasopressin", "TSH", "ACTH", "FSH", "MSH", "LH", "Prolactin", "Oxytocin"],
    "Thyroid": ["T3", "T4", "Calcitonin"],
    "Parathyroid": ["PTH", "Vasopressin"],
    "Thymus": ["Thymopoietin", "IGF", "THPO"],
    "Stomach": ["Gastrin", "Ghrelin", "Histamine", "Somatostatin"],
    "Adrenal": ["Androgens", "Glucocorticoids", "Adrenaline", "Noradrenaline", "Neuropeptide Y"],
    "Pancreas": ["Insulin", "Glucagon"],
    "Kidney": ["Somatostatin", "Calcitriol", "Renin", "Erythropoietin"],
    "Ovary": ["Estrogens", "Progesterone"],
    "Placenta": ["Estrogens", "Progesterone"],
    "Testes": ["Androgens"],
    "Uterus": ["Estradiol", "Inhibin", "Prolactin", "Relaxin"]
}
```
### 4. Requirements
'''
pip install easyocr
pip install langchain_groq
pip install transformers
