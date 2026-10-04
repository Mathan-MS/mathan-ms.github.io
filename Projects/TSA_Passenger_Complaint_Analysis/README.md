# AI-Based System for Residential Energy Efficiency Optimization

## Project Overview

This project develops a generative AI system that analyzes residential energy conditions and provides practical recommendations for improving household energy efficiency.

The system uses appliance energy consumption, indoor temperature, indoor humidity, outdoor temperature, and outdoor humidity to generate personalized energy-saving recommendations.

## Project Goals

- Analyze household energy conditions.
- Generate practical energy-saving recommendations.
- Reduce unsupported or inaccurate AI recommendations.
- Evaluate the model for response quality and hallucination risk.
- Present the final system through an interactive application.

## Dataset

The project uses the Appliances Energy Prediction dataset.

The primary variables include:

- Appliance energy consumption
- Indoor temperature
- Indoor humidity
- Outdoor temperature
- Outdoor humidity

## Tools and Technologies

- Python
- Pandas
- NumPy
- PyTorch
- GPT-2
- Hugging Face Transformers
- LoRA
- PEFT
- Streamlit
- Matplotlib
- Scikit-learn

## Repository Structure

- `notebooks/` – Jupyter notebooks
- `scripts/` – Python source code
- `data/` – Dataset information
- `results/` – Training and evaluation results
- `figures/` – Charts and application screenshots

## Responsible AI Considerations

The model's recommendations must be treated as general energy-efficiency guidance. Responses are evaluated for hallucination risk, unsupported claims, unsafe recommendations, and inconsistent output.
