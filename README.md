# Sentence Transformer Model Evaluation using TOPSIS

## Overview

This project evaluates multiple sentence transformer models using similarity metrics and ranks them using the **TOPSIS (Technique for Order Preference by Similarity to Ideal Solution)** method. The evaluation considers cosine similarity, Euclidean distance, inference time, and model size to determine the best model.

## Features

- Computes **cosine similarity** and **Euclidean distance** between sentence embeddings.
- Measures **inference time** for encoding sentences.
- Estimates **model size** in MB.
- Applies **TOPSIS ranking** to determine the best-performing model.
- Visualizes results using **seaborn** bar plots.

## Models Evaluated

- `all-MiniLM-L6-v2`
- `all-mpnet-base-v2`
- `distilbert-base-nli-stsb-mean-tokens`
- `bert-base-nli-mean-tokens`
- `roberta-base-nli-stsb-mean-tokens`

## Installation

Ensure you have Python installed (>=3.7), then install the required dependencies:

```bash
pip install numpy pandas sentence-transformers matplotlib seaborn torch
```

## Usage

Run the script to evaluate models and generate rankings:

```bash
python evaluate_models.py
```

## Explanation of TOPSIS Criteria

The TOPSIS method ranks models based on four key factors:

| Metric               | Weight | Impact  | Explanation |
|----------------------|--------|---------|-------------|
| Cosine Similarity   | 0.4    | + (Higher is better) | Measures how similar the sentence embeddings are. |
| Euclidean Distance  | 0.3    | - (Lower is better)  | Measures the absolute distance between embeddings. |
| Inference Time (ms) | 0.2    | - (Lower is better)  | Determines how fast the model processes input. |
| Model Size (MB)     | 0.1    | - (Lower is better)  | Evaluates memory efficiency. |

## Output Example

After running the script, the results are displayed in a table and bar plot:

```
                            Model  Cosine Similarity  Euclidean Distance  Inference Time (ms)  Model Size (MB)  TOPSIS Score
0  sentence-transformers/all-MiniLM-L6-v2            0.89                0.54                10.5              85.3         0.87
1  sentence-transformers/all-mpnet-base-v2           0.91                0.52                12.0              120.4        0.82
...
```

A visualization of the rankings is also displayed.

## License

This project is licensed under the MIT License.

## Contributing

Feel free to fork the repository and contribute improvements via pull requests!



