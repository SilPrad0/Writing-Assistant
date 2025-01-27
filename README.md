# Writing-Assistant 🚧 (under development) 🚧
(My first experiment with model fine-tuning ever) 😺

This repository contains a text-polishing model using the T5 architecture, implemented with PyTorch, Hugging Face, and Google Colab.
The project was born out of my need for a specialized tool to help polish scenes in my novel while simultaneously practicing my ML skills. 📚🤖 The model aims to polish raw text (scenes) by correcting grammar, enhancing readability, and refining the language.

This model fine-tunes the T5 transformer to take your rough drafts and make them sound more professional by focusing on grammar and style improvement. Well... I hope so 😕

## Setup

1. Clone the repository.
2. Install the required packages:
   ```bash
   pip install -r requirements.txt

## Training the Model
Clone the repository and install dependencies as mentioned above.
Prepare your dataset by following the instructions in sample_data.json. The data should contain raw scenes as input and the polished scenes as output.

## Model Evaluation and Results
The model’s performance is evaluated using the ROUGE metric, which compares the generated text with reference text (ground truth). You can track real-time training and evaluation metrics using Weights & Biases (W&B).

Live Metrics: Metrics such as loss and ROUGE scores are tracked on W&B for visualization and further analysis.
View my W&B experiment dashboard. ($$$)
