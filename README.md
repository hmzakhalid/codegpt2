# Fine-tuned GPT2 Model on Code using HuggingFace Transformers

This repository contains code for training and generating inferences from a fine-tuned GPT2 model. The model is specifically trained on code and natural language data to generate code snippets given natural language prompts.

## Dependencies

- Python 3.8 or higher
- PyTorch 1.9.0 or higher
- Transformers 4.28.0 or higher
- tqdm 4.65.0 or higher

## Code Explanation

The provided code consists of the following components:

1. **Loading pretrained GPT2 model and tokenizer**: The code loads the pretrained GPT2 model and tokenizer and adds special tokens for padding, start of sentence, and end of sentence.

2. **Fine-tuned GPT2 model and tokenizer**: The fine-tuned GPT2 model is created with additional special tokens and a larger vocabulary size to accommodate the new tokens.

3. **CodeData Dataset**: A custom PyTorch Dataset is defined to load code data from a JSON file, preprocess it, and tokenize it using the GPT2 tokenizer.

4. **Training the model**: The model is trained using the Adam optimizer on the CodeData dataset for a specified number of epochs.

5. **Inference function**: A function is defined to generate inferences given a prompt, model, and tokenizer. It takes parameters such as maximum length, number of return sequences, and temperature to control the output.

6. **Generating inferences**: The code generates example inferences using both the pretrained GPT2 model and the fine-tuned model, illustrating the difference in outputs.

## How to Use

1. Install the required dependencies.

2. Prepare a JSON file containing the code data with the following format:

```json
[
    {
        "instruction": "Instruction in natural language",
        "input": "Input description (optional)",
        "output": "Code snippet"
    },
    ...
]
```

3. Update the path to the JSON file in the CodeData class instantiation.

4. Run the script to train the model. The model's state will be saved after each epoch.

5. Use the generate_inference function to generate code snippets given natural language prompts.

