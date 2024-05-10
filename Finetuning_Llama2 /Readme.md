***Fine-tuning LLM***

**Steps to finetune Llama2:**

Step 1) Install All the Required Packages<br>

Step 2) Import All the Required Libraries<br>

Step 3) Load a llama-2-7b-chat-hf model (chat model)<br>
        Train it on the mlabonne/guanaco-llama2-1k (1,000 samples), which will produce our fine-tuned model Llama-2-7b-chat-finetune<br>
        QLoRA will use a rank of 64 with a scaling parameter of 16. We’ll load the Llama 2 model directly in 4-bit precision using the NF4         type and train it for one epoch<br>
        
Step 4) Load everything and start the fine-tuning process<br>
        First of all, we want to load the dataset we defined. Here, our dataset is already preprocessed but, usually, this is where you            would reformat the prompt, filter out bad text, combine multiple datasets, etc.<br>
        Then, we’re configuring bitsandbytes for 4-bit quantization.<br>
        Next, we're loading the Llama 2 model in 4-bit precision on a GPU with the corresponding tokenizer.<br>
        Finally, we're loading configurations for QLoRA, regular training parameters, and passing everything to the SFTTrainer.<br> 
        
Step 5) Use the text generation pipeline to ask questions.<br>

Step 6) Store New Llama2 Model (Llama-2-7b-finetuned).<br>

Step 7) Push Model to Hugging Face Hub.<br>
