# AI-Based Residential Energy Efficiency Optimization

## Project Overview

This project develops an AI-based residential energy-efficiency advisor using household energy and environmental sensor data.

The workflow transforms structured energy data into prompt-response examples and fine-tunes a GPT-2 language model with LoRA so the model can generate residential energy-efficiency assessments, recommendations, and limitations.

## Business Problem

Residential energy consumption can be difficult to interpret because household energy use is influenced by multiple environmental and behavioral factors.

This project is aimed at accomplishing the following goals:

- Convert household energy and environmental data into structured prompts.
- Fine-tune GPT-2 using LoRA.
- Generate energy-efficiency assessments and recommendations.
- Compare the fine-tuned model with the original GPT-2 baseline.
- Evaluate response structure and hallucination risk.
- Save and reload the trained LoRA adapter.

## Dataset

The project uses:

`KAG_energydata_complete.csv`

The dataset contains household appliance energy consumption together with temperature and humidity measurements collected from multiple rooms and environmental sensors.

## Tools & Technologies

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- PyTorch
- Hugging Face Transformers
- PEFT / LoRA
- GPT-2

## Project Workflow

The project follows these main steps:

1. **Data Preparation**
   - Loaded household energy and environmental sensor data.

2. **Feature Categorization**
   - Converted selected numeric measurements into descriptive categories.

3. **Prompt and Response Generation**
   - Built structured training examples with assessments, recommendations, and limitations.

4. **Baseline Evaluation**
   - Evaluated the original GPT-2 model before fine-tuning.

5. **LoRA Fine-Tuning**
   - Fine-tuned GPT-2 using parameter-efficient LoRA adapters.

6. **Model Evaluation**
   - Compared training and validation performance.
   - Compared baseline and fine-tuned responses.

7. **Format Compliance Testing**
   - Checked whether responses followed the expected structure.

8. **Hallucination-Risk Testing**
   - Tested the model for unsupported or exaggerated claims.

9. **Model Saving and Reload Verification**
   - Saved and reloaded the trained LoRA adapter.

## Model Evaluation

The model was evaluated using:

- Training Loss
- Validation Loss
- Baseline vs Fine-Tuned Response Comparison
- Format Compliance
- Hallucination-Risk Testing
- Reload Verification

## Key Findings

The project demonstrates that GPT-2 can be adapted to a specialized residential energy-efficiency use case using LoRA.

The fine-tuned workflow provides structured energy-efficiency guidance while also allowing response format and hallucination risk to be reviewed.

## Outcome

This project demonstrates a complete generative-AI workflow for residential energy-efficiency guidance.

The final workflow includes data preparation, prompt engineering, GPT-2 LoRA fine-tuning, model evaluation, hallucination-risk testing, and model persistence.

## Installation / Running the Project

1. Clone the repository:

```bash
git clone <repo_url>
cd <repository_name>
```

2. Place the dataset in the `data/` folder.

3. Install the required packages:

```bash
pip install -r requirements.txt
```

4. Launch Jupyter Notebook:

```bash
jupyter notebook
```

5. Open and run:

`notebooks/Energy_Efficiency_Optimization.ipynb`
