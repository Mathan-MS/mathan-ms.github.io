# AI-Based Residential Energy Efficiency Optimization

## Project Overview

This project developed a generative AI advisor that uses household energy and environmental readings to produce residential energy-efficiency assessments, recommendations, and limitations. It converts structured sensor measurements into prompt-response examples and fine-tunes GPT-2 using Low-Rank Adaptation (LoRA).

The work demonstrates prompt engineering, parameter-efficient language-model fine-tuning, qualitative response evaluation, hallucination-risk testing, and model persistence. It does **not** estimate verified household energy or cost savings.

## Business Problem

Household energy readings alone can be difficult to translate into practical guidance. This project explored whether a fine-tuned language model could turn selected readings into consistently structured recommendations while acknowledging what those readings cannot establish.

The completed workflow prepared training examples, compared original GPT-2 with the fine-tuned model, checked response formatting and unsupported claims, and saved and reloaded the LoRA adapter.

## Dataset

The project uses the Appliances Energy Prediction dataset, stored as `data/KAG_energydata_complete.csv`.

- **Source records:** 19,735
- **Valid records retained:** 19,735
- **Selected measurements:** Five — appliance energy use, indoor temperature, indoor humidity, outdoor temperature, and outdoor humidity
- **Generated balanced examples:** 510, drawn from four appliance-energy categories
- **Training / validation split:** 459 / 51 examples

Numerical readings were categorized and combined with rule-generated assessments, recommendations, and limitations to create the model's training examples. The generated responses are instructional examples, not independently verified energy-saving interventions.

## Tools & Technologies

- Python and Jupyter Notebook
- pandas and NumPy
- Matplotlib
- PyTorch
- Hugging Face Transformers
- PEFT / LoRA
- GPT-2

## Project Workflow

1. **Data preparation:** Loaded and validated household appliance-energy and environmental measurements.
2. **Feature categorization:** Converted selected numerical readings into descriptive energy and environmental categories.
3. **Prompt-response construction:** Created structured examples with *Assessment*, *Recommendations*, and *Limitations* sections.
4. **Baseline evaluation:** Generated original GPT-2 responses for comparison.
5. **LoRA fine-tuning:** Trained parameter-efficient adapters on the generated examples.
6. **Model evaluation:** Reviewed training and validation losses and compared responses on five scenarios.
7. **Format and hallucination-risk checks:** Evaluated required headings and tested four requests that could encourage unsupported claims.
8. **Model persistence:** Saved and successfully reloaded the LoRA adapter and tokenizer.

## Model Evaluation

| Measure | Saved notebook result |
|---|---:|
| Training examples | 459 |
| Validation examples | 51 |
| Training epochs | 3 |
| Training steps | 171 |
| Average training loss | 1.230053 |
| Final logged training loss | 0.435900 |
| Final validation loss | 0.216380 |
| Baseline comparison scenarios | 5 |
| Hallucination-risk tests | 4 |
| Saved adapter reload | Passed |

These loss values measure optimization on the constructed language-model dataset. They are **not** prediction accuracy, evidence of recommendation correctness, or estimates of energy savings.

## Key Findings

- The pipeline retained all **19,735** source records and constructed **510** balanced prompt-response examples across four appliance-energy categories.
- GPT-2 LoRA fine-tuning completed **3 epochs and 171 steps**, with average training loss **1.230053** and final validation loss **0.216380**.
- The original and fine-tuned models were compared on **five** energy-use scenarios, and **four** targeted hallucination-risk tests were performed.
- The saved LoRA adapter reloaded successfully, and its sample response contained the required **Assessment**, **Recommendations**, and **Limitations** headings.
- The reloaded response also contained repeated wording and inconsistent numbering. Passing a format check therefore did not demonstrate consistently polished or reliable advice.

## Outcome

The project produced an end-to-end generative AI workflow, including a fine-tuned GPT-2 LoRA adapter, a training/validation loss figure, model-response comparison tables, format-compliance results, and hallucination-risk evaluation outputs.

The work demonstrates the feasibility of generating structured residential energy guidance from selected sensor readings. Before practical use, the recommendations would require broader testing, expert review, and separate measurement of actual energy outcomes.

## Installation / Running the Project

The project is located in the `Projects/Residential_Energy_Efficiency` directory of the portfolio repository. The notebook expects the dataset in `data/` and saves artifacts to `figures/`, `results/`, and `models/`.

### Prerequisites

- **Python 3.11** (recommended, subject to dependency compatibility)
- **Git** — Available from [git-scm.com](https://git-scm.com/downloads)

### Step 1: Clone the Repository

```bash
git clone https://github.com/Mathan-MS/mathan-ms.github.io.git
cd mathan-ms.github.io/Projects/Residential_Energy_Efficiency
```

### Step 2: Install Project Dependencies

```bash
python -m pip install -r requirements.txt
```

### Step 3: Launch Jupyter Notebook

```bash
python -m notebook
```

### Step 4: Open and Run the Notebook

Open `notebooks/Residential_Energy_Efficiency.ipynb`, select the appropriate Python kernel, and use **Kernel → Restart Kernel and Run All Cells**. The notebook saves evaluation results in `results/`, generated figures in `figures/`, and the trained LoRA adapter and tokenizer in `models/` for later use.

**Note:** Execution time varies with hardware and available resources. Model downloads and fine-tuning can take additional time, particularly on CPU.
