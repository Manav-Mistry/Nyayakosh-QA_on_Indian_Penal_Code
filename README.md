# Nyayakosh : Question Answering Tool on Indian Penal Code
question answering on Indian Penal Code using Retrieval Augmented Generation

## Motive of the Project

The Indian Penal Code (IPC) is a comprehensive legal document with 511 sections and 23 chapters, making it both lengthy and complex. For lawyers, law students, and anyone seeking legal clarity, it can be daunting to remember or quickly locate the relevant sections. This challenge often leads to inefficiencies in understanding or applying the law effectively.

To address this issue, our Retrieval Augmented Generation (RAG) application simplifies the process by providing precise, contextually accurate answers. By combining advanced retrieval techniques with generative models, it helps save time and makes the IPC more accessible for study and practice.

## Dataset
The dataset is uploaded as pdf named THE-INDIAN-PENAL-CODE-1860. 

## Why Retrieval Augmented Generation (RAG) Approach?  
Initially, research focused on fine-tuning a pretrained model to adapt it to the task of question answering on a custom dataset. However, fine-tuning proved unsuitable for this specific task, as it often led to vague answers influenced by the model's pretrained knowledge rather than the custom dataset.  

An alternative approach was identified through research on effective methods for handling question answering on custom datasets, particularly focusing on the In-Context Learning (ICL) method.  

### What is the ICL Method?  
- This method works by providing context alongside the user's query:  
  1. Relevant context is identified for the question.  
  2. The context and query are fed to a language model.  
  3. The model generates answers strictly based on the provided context.  

### Benefits of the ICL Method  
- Generates answers solely from the provided context, significantly reducing hallucination.  

### Challenges in Implementing ICL  
- When dealing with extensive datasets, it becomes impractical to provide the entire dataset as context (e.g., thousands of pages).  

### Enter RAG  
The RAG approach resolves this limitation. The data, split into smaller chunks, is stored in a vector database. When a query is made, only the most relevant chunks are retrieved from the database. These chunks are then used by the language model to construct a precise and contextually accurate answer.


## Embedding Model
Embedding model used is BAAI/bge-base-en-v1.5 model.

## Model for Inference
Language model for inference is instruct model by Mistral "mistralai/Mistral-7B-Instruct-v0.2"

## Evaluation
Evaluation Metrics are Faithfulness score and Relevancy score. Both of them are 0.9 in this case. 
Model used for evaluation is GPT-4.

## How to Run
This is a notebook for step by step execution. You just need Hugging face API token for inference as it runs on hugging face server.

## Future Enhancements
- Having an interactive web-based UI for end user.
- Expanding the corpus to include more legal documents and case laws.

## Contributing
Contributions are welcome! Please follow the guidelines in `CONTRIBUTING.md`.

## Detailed Explanation
Take a look at uploaded pdf named Nyayakosh for in-depth explanation about project, what is RAG and why a particular method is being used.
