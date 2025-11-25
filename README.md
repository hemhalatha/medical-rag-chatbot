# **Medical RAG System Using MedlinePlus XML & FAISS**

This project demonstrates a complete Retrieval-Augmented Generation (RAG) pipeline built using **MedlinePlus XML medical data**, **sentence chunking**, **sentence-level embeddings**, and a **FAISS vector store**.
It includes two notebooks:

* **XML to FAISS DB Creator**
* **RAG System Using FAISS**

Anyone can use the notebooks to extract medical knowledge, build a vector database, and run RAG-based question answering.

---

## **Overview**

This repository contains an end-to-end Medical RAG system trained entirely on **MedlinePlus medical articles** sourced from XML. The system is built to:

* Extract and clean medical text from XML
* Convert content into structured chunks
* Generate embeddings
* Store vectors using a **FAISS index**
* Retrieve the most relevant medical information
* Pass the retrieved data to an LLM for factual, context-bounded answers

The model answers strictly from the retrieved content to avoid hallucinations.

---

## **Features**

* **XML Parsing**
  Extract clean medical text from MedlinePlus XML.

* **Sentence-Level Chunking**
  Ensures high-quality, precise retrieval for medical queries.

* **Embedding Generation**
  Works with any embedding model of choice.

* **FAISS Vector Store**
  Stores >50k chunks efficiently.

* **RAG Pipeline**
  Combines retrieval + generative model for grounded medical answers.

---

## **Files Included**

### **1. `XML_to_FAISS_DB.ipynb`**

Responsible for:

* Loading the MedlinePlus XML
* Extracting and cleaning content
* Chunking into sentences
* Creating embeddings
* Building `medline_faiss.index`
* Saving `medline_chunks.json` to Google Drive

### **2. `Medical_RAG_System.ipynb`**

Responsible for:

* Loading the FAISS index + chunks
* Creating an efficient retriever
* Building prompts
* Running the RAG pipeline
* Producing medically accurate answers based on the database

---

## **How to Use**

### **1. Upload XML File (if needed)**

Place your XML file in Google Drive:

```
/content/drive/MyDrive/mplus_topics_2025-11-20.xml
```

### **2. Run Notebook 1**

Generates:

```
medline_faiss.index
medline_chunks.json
```

### **3. Run Notebook 2**

Loads your FAISS DB and starts answering queries.

Example:

```python
ask_rag("What is abdominal pain?")
```

---

## **Output Example**

```
CONTEXT MATCHED:
- Retrieved sentences related to abdominal pain
- Non-hallucinated, medically grounded explanation

FINAL ANSWER:
Abdominal pain refers to discomfort in the area between the chest and pelvis...
```

---

## **Technologies Used**

* **Python**
* **FAISS**
* **Sentence Transformers**
* **Google Colab**
* **MedlinePlus XML Dataset**
* **LLM (Gemini/OpenAI compatible)**

---

## **License**

This project is for **educational and research purposes only**
and **should not be used as a substitute for professional medical advice**.


