# README: Gland-Hormone Extraction Using OCR, Meta LLaMA 3.1 70B, and Groq for Fast LBU-Based Inferencing

## Project Overview
This project aims to extract relationships between human glands and the hormones they secrete from images. We use **Optical Character Recognition (OCR)** for extracting text from images and the **Meta LLaMA 3.1 70B** language model to identify the relationships between glands and hormones. To optimize processing time, we leverage **Groq's LBU-based (Latency-Bound Unit) system** for fast model inferencing. The final goal is to produce a structured **JSON** output that lists glands as keys and their respective hormones as values.

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
- **Prompt Design**: A prompt is carefully designed to guide the Meta LLaMA model to extract gland-hormone relationships and format the result into structured **JSON**. This ensures that the model understands the task and provides the necessary information in the correct format.
- **Generating Output**: The model's output is processed and formatted into a JSON structure, where glands are the keys, and the corresponding hormones are the values.

### 3. JSON Output
The final output is a well-organized **JSON** structure that maps glands to the hormones they secrete. The format is as follows:

```json
{
    "Gland Name 1": ["Hormone A", "Hormone B"],
    "Gland Name 2": ["Hormone C", "Hormone D"]
}
# README: Gland-Hormone Extraction Using Meta LLaMA 3.1 70B and Groq's LBU-Based Inferencing

## Why We Use Groq's LBU-Based Inferencing
Using **Groq's LBU-based inferencing** significantly improves the performance of the **Meta LLaMA model** by:

- **Reducing Latency**: Groq’s **Latency-Bound Units (LBUs)** are designed to minimize the delay in model execution, allowing us to process input in real time or near real time.
- **Optimized Performance**: Groq accelerates the performance of large models like **Meta LLaMA 3.1 70B**, enabling it to handle complex and large-scale text data efficiently.
- **Improved Efficiency**: The combination of **LangChain** and **Groq** ensures that our system can handle demanding language model tasks, such as extracting detailed relationships from large bodies of text, without sacrificing speed or accuracy.

## Candidate Assessment
This project is part of an open-ended assessment designed to evaluate candidates’ skills in **problem-solving**, **innovation**, and **technical aptitude**. Candidates are encouraged to explore different methods for preprocessing, structuring, or analyzing the text data extracted from images. By leveraging **OCR**, **LLMs**, and **fast inferencing through Groq**, candidates can demonstrate their ability to work with cutting-edge technology in real-world applications.

## Requirements
- Python 3.x
- EasyOCR
- LangChain with Groq integration (for Meta LLaMA 3.1 70B inferencing)
- Transformers library

## Installation
To install the necessary libraries, use the following commands:

pip install easyocr
pip install langchain_groq

## Conclusion
This project demonstrates the successful integration of **OCR technology** and **large language models (LLMs)**, specifically the **Meta LLaMA 3.1 70B**, to extract meaningful relationships between glands and the hormones they secrete from images. By leveraging **Groq's LBU-based inferencing**, we were able to significantly optimize the process for speed and efficiency, ensuring faster execution without compromising on accuracy.

The solution highlights the powerful combination of **OCR**, **LLMs**, and **high-performance inferencing** to solve real-world challenges in a timely manner, showcasing the potential of advanced AI in delivering structured, actionable insights from complex data sources.
