# Information Retrieval from PDF with Sentence Transformers

This repository contains a Python notebook (sentence_transform_PDF.ipynb) that demonstrates the use of Sentence Transformers for Information Retrieval from PDF documents. The notebook is designed to run on the Google Colab platform.

## 1. Runtime Performance

To optimize computational performance, change the "Runtime Type" in the Google Colab notebook. In the menu, go to "Runtime" and set "Runtime Type" to "T4 GPU". Note that full GPU performance is only available on 'Pay As You Go' registration.

## 2. Install Required Libraries

This notebook relies on the following libraries:

`!pip install -U sentence-transformers`
`!pip install PyPDF2`

## 3. Import Dependencies

The notebook uses the following Python libraries:

`import os`
`import PyPDF2`
`from sentence_transformers import SentenceTransformer, util`
`import torch`
`import spacy`
`from google.colab import drive`

## 4. Prepare Source Data on Google Drive

Ensure that your PDF files are available on Google Drive. Create a source folder (e.g., 'pdf_folder') and upload PDF files (e.g., scientific papers) into it.

## 5. Mount Google Drive

Run the code to mount your Google Drive in the Colab notebook. Follow the link that appears, enter the authorization code, and confirm access to your Google Drive account.

`drive.mount('/content/drive')`

## 6. Access PDF Files

Once your Google Drive is mounted, access data from the specified source folder ('pdf_folder').

`folder_path = '/content/drive/My Drive/pdf_folder'`
`pdf_files = os.listdir(folder_path)`

## 7. Load SentenceTransformer Models

Load specific pre-trained SentenceTransformer models. Comment/uncomment the desired model.

`model = SentenceTransformer('all-MiniLM-L6-v2')`

For more details on the models, visit [Hugging Face Sentence Transformers](https://huggingface.co/sentence-transformers).

## 8. Main Program Code

The main program code performs the following steps:

1. Retrieve text data from PDF files.
2. Obtain related phrases based on the initial question.
3. Filter output to include only phrases most relevant to the terms in the initial question.
4. Use a threshold to filter related phrases based on similarity scores to the initial question.
5. Print only phrases with similarity scores above the threshold.
6. For a detailed breakdown of the main program code, refer to the notebook.

**Function Call**

To use the information retrieval function, provide a question and a similarity score threshold.

`retrieve_information("Your question...", 0.6)`

Adjust the question and threshold as needed. The function retrieves and outputs the most relevant text passages based on the input question and specified similarity score threshold.





