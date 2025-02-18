# Writing-Assistant 🚧 (under development) 🚧
(My first experiment with model fine-tuning ever) 😺

This repository contains a text-polishing model using the T5 architecture, implemented with PyTorch, Hugging Face, and Google Colab.
The project was born out of my need for a specialized tool to help polish scenes in my novel while simultaneously practicing my ML skills. 📚🤖 The model aims to polish raw text (scenes) by correcting grammar, enhancing readability, and refining the language.

This model fine-tunes the T5 transformer to take your rough drafts and make them sound more professional by focusing on grammar and style improvement. ~~I'm in no way implying that human editors should be replaced--in fact, I would very much like one, I'm just on a budget and want to finish my novel in my lifetime.~~ 😅 

## Why fine-tune a model instead of using pre-trained models online?
- Pre-trained models are general-purpose and may not fully capture the nuances of creative writing or the specific style of my novel.
- I can adjust the level of creativity or conservatism in the edits.
- One of **_the key advantages_** of fine-tuning my own model is the ability to **avoid the censorship** and content restrictions that come with pre-trained models hosted online. Many online models have strict guidelines that can flag or block text unnecessarily. This gives me the freedom to explore complex or emotional scenes while maintaining full control over the editing process.
- **Privacy**
- Learning and Skill Development 😸
## A little breakdown of the process

### **Data Collection and Preprocessing:**   
_Dataset:_ I created a dataset of input-output pairs, where the input is a raw draft and the output is a professionally edited version. These pairs were carefully curated to capture the nuances of creative writing, including dialogue, descriptions, and narrative structure.  

_Data Augmentation:_ To enhance the dataset, I used techniques like back translation (translating text to another language and back to English) and synonym replacement. This introduced variability and improved the model’s ability to generalize.

_Tokenization:_ The text was tokenized using the T5 tokenizer, which converts raw text into subword tokens compatible with the model.
### **Model Fine-Tuning:**     
_Model Architecture:_ I fine-tuned the T5-small model, a smaller variant of T5 that balances performance and computational efficiency.

_Training Framework:_ Using Hugging Face’s Transformers library, I trained the model on my dataset with a sequence-to-sequence objective. The model learned to map raw drafts to polished edits, capturing patterns like adding sensory details, improving sentence flow, and enhancing emotional depth.

Hyperparameters:

- Batch size: 16
- Learning rate: 3e-4
- Epochs: 5 (with early stopping to prevent overfitting)
- Optimizer: AdamW

Training Environment: The model was trained on Google Colab with GPU acceleration, ensuring efficient training despite resource constraints.

### **Inference:**  
Once trained, the model can take a raw draft as input and generate a refined version. For example:
| Raw Input | Polished Output |
|-----------|-----------------|
| "camping is set up, a light breeze filled with piney and earthy scents anoints the scene." | "The campsite was alive, the breeze carrying piney and earthy scents that wrapped around them like a soft, familiar embrace." |

## Technical Details
Model: T5-small (fine-tuned for novel editing)

Framework: Hugging Face Transformers

Training Data: 1,000+ input-output pairs (expanded using back translation and synonym replacement)

Evaluation Metrics:

BLEU Score: Used to measure the similarity between the model’s output and the target text.

Qualitative Assessment: Manual evaluation of generated edits to ensure they align with the desired style and tone.

Training Environment: Google Colab (with GPU acceleration)
