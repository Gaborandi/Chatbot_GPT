# Chatbot_GPT
Create a Chatbot using GPT-2 model on your custom unlabeled dataset

## A detailed explanation of the code:

1- Import necessary libraries and modules:

- torch: PyTorch library for deep learning.
- GPT2LMHeadModel, GPT2Tokenizer, GPT2Config: Hugging Face Transformers classes for GPT-2 model, tokenizer, and configuration.
- TextDataset, DataCollatorForLanguageModeling: Hugging Face Transformers classes for creating a dataset and data collator for language modeling.
- Trainer, TrainingArguments: Hugging Face Transformers classes for creating a trainer and setting up training arguments.
- pandas: Library for data manipulation and analysis.
- Dataset: PyTorch class for creating a custom dataset.

2- Read the dataset pubmed.csv using pandas and store it in df.

3- Define the read_data function that takes a DataFrame and returns the "text" column.

4- Define the TextDataset class, which inherits from PyTorch's Dataset class, to create a custom dataset for the GPT-2 model.

- __init__: Initialize the dataset with the tokenized encodings.
- __getitem__: Get an item from the dataset by its index.
- __len__: Get the length of the dataset.

5- Define the train_gpt2 function to fine-tune the GPT-2 model on the given dataset:

- Load the tokenizer and configuration for the specified model name.
- Load the GPT-2 model using the configuration.
- Set the padding token to be the same as the end-of-sentence (EOS) token.
- Tokenize the input texts, create the dataset, and create a data collator for language modeling.
- Set up training arguments, including the output directory, number of epochs, batch size, and learning rate.
- Create a trainer instance with the model, training arguments, data collator, and dataset.
- Train the model and save the model and tokenizer to the output directory.

6- Define the chat function to generate responses from the fine-tuned GPT-2 model:

- Tokenize the input text and generate a response using the model.
- Adjust the generation parameters, such as temperature and top_k, to control the randomness and diversity of the responses.
- Decode the generated response and remove special tokens.

7 - In the main block:

- Read the dataset and extract the text data.
- Set the model name to "gpt2-medium" and specify the output directory.
- Fine-tune the GPT-2 model using the dataset and the specified parameters.
- Load the fine-tuned model and tokenizer from the output directory.
- Start an interactive chat loop, taking user input, generating responses using the chat function, and printing the responses.


## With this code, you can fine-tune a GPT-2 model on your dataset and interact with the fine-tuned model to generate responses.
