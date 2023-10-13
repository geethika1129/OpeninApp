# OpeninApp
## Task:<br>
Create a Hinglish translation from English text. The text should sound natural and also convert all the difficult words and phrases in English to Hinglish. This converted text should be easy to understand for even a non-native Hindi speaker.
<br>
<br>
## Model
We embarked on a natural language processing project using the Hugging Face Transformers library to build a translation model. The goal was to train a model that could translate English sentences to Hinglish, a colloquial mix of Hindi and English. To accomplish this, we followed a systematic process:

Step 1: Dataset Acquisition
We began by acquiring our dataset, which contained pairs of English and Hinglish translations. To do this, we utilized Hugging Face's dataset repository, making use of a JSON file containing the translations which can be found here :<br>
https://huggingface.co/datasets/findnitai/english-to-hinglish


Step 2: Tokenization
Tokenization is a crucial part of any NLP project. We employed a T5 (Text-to-Text Transfer Transformer) tokenizer to preprocess the text data. The tokenizer was responsible for converting raw text inputs into a tokenized format that the transformer model could understand.

Step 3: Data Preprocessing
Data preprocessing was an essential step in preparing the dataset for model training. To ensure the data was in the correct format, we implemented a preprocessing function. Within this function, we performed tokenization on both the input text and the target text. Additionally, we applied necessary preprocessing steps such as padding sequences to make them uniform in length.

Step 4: Data Collation
With our data preprocessed, we created a data collator using Hugging Face's DataCollatorForSeq2Seq. The data collator played a vital role in handling various aspects of the data, including padding, truncation, and formatting the preprocessed data into batch-friendly sequences.

Step 5: Setting Training Arguments
Our next step was configuring the training process. We defined a dictionary named trainer_args_in to set important training arguments. These arguments included specifying the output directory for model checkpoints, indicating whether we should overwrite the output directory, training batch size, and the number of training epochs.

Step 6: Model Initialization
For our translation task, we needed a transformer model. We initialized a T5 model using Hugging Face's model library. The model served as the core component of our translation system.

Step 7: Training Configuration
To bring all the components together, we set up a Seq2Seq trainer. This trainer was responsible for configuring the model, incorporating the training arguments, connecting the training data, and orchestrating the entire training process. The trainer also relied on the tokenizer and data collator for data preparation.

Step 8: Training Loop
With our training configuration in place, we initiated the training process by calling trainer.train(). This command triggered the training loop, during which the model was trained on the provided dataset using the configured settings.

Step 9: Model Saving
Upon completing the training process, we ensured to save the trained model for future use. We used the trainer.save_model() method to save the model's parameters and architecture.

Some sample Outputs :

![Screenshot (81)](https://github.com/geethika1129/OpeninApp/assets/83590629/587bcc6b-7a11-4c6e-b05a-ab2e582f122c)
![Screenshot (82)](https://github.com/geethika1129/OpeninApp/assets/83590629/886b48e3-409b-46ab-8d9f-a70ad32b91db)
![Screenshot (83)](https://github.com/geethika1129/OpeninApp/assets/83590629/574ceb79-a53a-4110-909a-5e4f71c6699d)
