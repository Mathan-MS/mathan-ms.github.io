# AI-Based Residential Energy Efficiency Optimization

## Project Overview

This project develops an AI-based residential energy-efficiency advisor using household energy and environmental sensor data. The workflow transforms structured energy data into prompt-response examples and fine-tunes a GPT-2 language model with LoRA so the model can generate residential energy-efficiency assessments, recommendations, and limitations.

The project includes data preparation, prompt construction, model training, evaluation, hallucination-risk testing, model saving, and reload verification.

## Business Problem

Residential energy consumption can be difficult to interpret because household energy use is influenced by multiple environmental and behavioral factors. The goal of this project is to explore whether a lightweight fine-tuned language model can convert household energy data into structured, understandable energy-efficiency guidance.

The model is designed to generate responses that include:

- An assessment of the household energy situation
- Practical energy-efficiency recommendations
- Limitations or cautions associated with the recommendation

## Dataset

The project uses:

`KAG_energydata_complete.csv`

The dataset contains household appliance energy consumption along with temperature and humidity measurements collected from multiple rooms and environmental sensors.

The notebook reads the source data from the project's `data/` folder and transforms the records into structured text examples for model training and evaluation.

## Methods

The project follows these main steps:

1. **Data Preparation**  
   Load and prepare household energy and environmental sensor data for analysis.

2. **Feature Categorization**  
   Convert selected numeric energy and environmental measurements into meaningful descriptive categories that can be incorporated into natural-language prompts.

3. **Prompt and Response Generation**  
   Build structured examples that describe household conditions and pair them with energy-efficiency assessments and recommendations.

4. **Model Fine-Tuning**  
   Fine-tune GPT-2 using LoRA to create a lightweight domain-adapted energy-efficiency advisor.

5. **Model Evaluation**  
   Evaluate training and validation performance and compare the fine-tuned model with the original GPT-2 baseline.

6. **Format Compliance Testing**  
   Check whether generated responses follow the expected assessment, recommendation, and limitation structure.

7. **Hallucination-Risk Testing**  
   Test the model on selected prompts to identify unsupported, exaggerated, or unreliable recommendations.

8. **Model Saving and Reload Verification**  
   Save the trained LoRA adapter and verify that it can be reloaded for future inference.

## Tools and Technologies

- Python
- Jupyter Notebook
- pandas
- NumPy
- Matplotlib
- PyTorch
- Hugging Face Transformers
- PEFT / LoRA
- GPT-2

## Project Outputs

The notebook saves project outputs into dedicated folders.

### Figures

`figures/`

- `training_validation_loss.png`

### Results

`results/`

- `training_validation_metrics.csv`
- `model_response_comparison.csv`
- `format_compliance_summary.csv`
- `hallucination_risk_comparison.csv`

### Models

`models/`

- Training checkpoints
- Final GPT-2 LoRA adapter

## Repository Structure

```text
Energy_Efficiency_Optimization/
│
├── README.md
│
├── data/
│   └── KAG_energydata_complete.csv
│
├── figures/
│   └── training_validation_loss.png
│
├── results/
│   ├── training_validation_metrics.csv
│   ├── model_response_comparison.csv
│   ├── format_compliance_summary.csv
│   └── hallucination_risk_comparison.csv
│
├── models/
│   ├── checkpoints/
│   └── gpt2_energy_lora_adapter/
│
└── notebooks/
    └── Energy_Efficiency_Optimization.ipynb
```

## How to Run the Project

1. Clone the repository.

2. Place the dataset in the `data/` folder:

```text
data/KAG_energydata_complete.csv
```

3. Install the required Python packages:

```bash
pip install pandas numpy matplotlib torch transformers peft datasets accelerate
```

4. Open the notebook:

```text
notebooks/Energy_Efficiency_Optimization.ipynb
```

5. Run the notebook cells in order.

The notebook automatically creates the required `figures`, `results`, and `models` folders if they do not already exist.

## Key Skills Demonstrated

- Data preparation and transformation
- Feature categorization
- Prompt engineering
- Generative AI
- Large language model fine-tuning
- LoRA / parameter-efficient fine-tuning
- Model evaluation
- Hallucination-risk assessment
- Model persistence and reload testing
- Python-based machine learning workflow

## Outcome

The project demonstrates how a compact language model can be adapted to a specialized energy-efficiency use case using structured household energy data. The final workflow produces a reusable fine-tuned model, evaluation results, and supporting visualizations while also examining response quality and hallucination risk.

## Limitations

The model is intended as a demonstration of AI-assisted energy-efficiency guidance. Its recommendations depend on the quality and coverage of the training examples and should not be treated as a substitute for a professional home energy audit or engineering assessment.

## Future Improvements

Potential future enhancements include:

- Expanding the training dataset with a wider range of household conditions
- Testing additional language models
- Improving recommendation specificity
- Adding quantitative energy-saving estimates
- Expanding hallucination and safety evaluation
- Developing an interactive user interface for household energy recommendations
