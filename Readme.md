<h1 align="center">📝 Text Summarization 📚</h1>

<p align="center">
  A Python-based implementation of text summarization that supports both English and Bangla text using cosine similarity and PageRank.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-blue" />
  <img src="https://img.shields.io/badge/NLTK-3.5-green" />
  <img src="https://img.shields.io/badge/langdetect-1.0.9-orange" />
  <img src="https://img.shields.io/badge/NumPy-1.21-lightblue" />
  <img src="https://img.shields.io/badge/NetworkX-2.6-blue" />
</p>

---

## 📖 Overview

This project implements a **Text Summarization** system capable of processing both **English** and **Bangla** texts. It uses **Cosine Similarity** to measure the similarity between sentences and **PageRank** to rank these sentences for generating concise summaries.

## 💡 Features

- **Multi-Language Support**: Processes both English and Bangla texts.
- **Stopwords Handling**: Utilizes language-specific stopwords for more accurate similarity measurements.
- **Sentence Tokenization**: Efficiently splits documents into sentences for analysis.
- **Similarity Calculation**: Computes similarity between sentences using cosine distance.
- **Summary Generation**: Extracts the most significant sentences to create a clear summary.

## 🛠️ Technologies Used

- **Python**: Core programming language for the implementation.
- **NLTK (Natural Language Toolkit)**: For English stopwords and text processing.
- **langdetect**: To detect the language of the input text.
- **NumPy**: Used for matrix operations.
- **NetworkX**: To create and analyze the sentence similarity graph using PageRank.

---

## 🚀 How It Works

1. **Language Detection**: Automatically detects the language of the input text (English or Bangla).

2. **Article Preprocessing**: The input document is read and split into sentences based on language-specific punctuation.

3. **Sentence Similarity Calculation**: The similarity between each pair of sentences is computed using **Cosine Similarity**. Sentences are transformed into vectors, and the cosine of the angle between these vectors provides a similarity score.

4. **Graph Construction and Ranking**: The similarity scores form a graph, with sentences as nodes and edges representing the similarity. **PageRank** is applied to rank the sentences.

5. **Summary Generation**: The top N ranked sentences are selected to create the summary.

---

## ⚙️ How to Run

Follow these steps to run the summarization system locally:

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/basharul2002/Text-Summarization.git
```

### 2️⃣ Install Dependencies

Ensure you have the required libraries installed:
```bash
pip install numpy nltk langdetect networkx
```

### 3️⃣ Download NLTK Resources

Since the system uses NLTK’s stopwords, download the required resources:
```python
import nltk
nltk.download('stopwords')
```

### 4️⃣ Prepare Bangla Stopwords

Create a file named `bangla_stopwords.txt` in the `./sample/` directory and populate it with Bangla stopwords, one word per line.

### 5️⃣ Run the Python Script

You can summarize English and Bangla texts by providing the respective file paths. Execute the script as follows:
```python
python text_summarizer.ipynb
```

### 6️⃣ Input Files and Summary

The script can process two example files:
- `./sample/english_text.txt` (English text)
- `./sample/bangla_text.txt` (Bangla text)

The top N sentences will be extracted as the summary.

---

## 📂 Directory Structure

```
Text-Summarization/
│
├── sample/
│   ├── bangla_stopwords.txt        # Bangla stopwords file
│   ├── english_text.txt            # Sample English text file
│   └── bangla_text.txt             # Sample Bangla text file
├── text_summarizer.py              # Main Python script
└── README.md                       # Documentation
```

---

## 📊 Example Output

For an input English text, the output will be:
```bash
Detected language: en
Summary:
This is the first sentence of the summary. This is the second sentence of the summary.
```

For an input Bangla text, the output will be:
```bash
Detected language: bn
সারাংশ:
এটি সারাংশের প্রথম বাক্য। এটি সারাংশের দ্বিতীয় বাক্য।
```