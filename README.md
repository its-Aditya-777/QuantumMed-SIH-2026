# QuantumMed - Hybrid Quantum-Classical Multimodal Parkinson's Screening

QuantumMed is a research screening and decision-support prototype developed by ThunderStars for Smart India Hackathon 2026 - Problem Statement 26139.

It combines four biomedical signal pathways:

- Voice
- Gait
- Handwriting
- Resting-State EEG

into one integrated and explainable assessment.

## Overview

Different biomedical signals have different mathematical structures. QuantumMed therefore uses specialized models for each modality and combines their outputs at the decision-fusion layer.

Patient Inputs -> Specialized Models -> Validation-Weighted Fusion -> Pattern Index -> Unified Report

## Architecture

### Voice
- Random Forest
- 4-qubit Variational Quantum Classifier (VQC)
- Fidelity-Kernel Quantum SVM (QSVM)

### Gait
- RBF-SVM

### Handwriting
- Random Forest

### EEG
- Logistic Regression

Available modality scores are combined using validation-weighted late fusion.

If one or more modalities are unavailable, the remaining contribution weights are automatically re-normalized.

## Quantum Voice Core

The Voice branch contains QuantumMed's quantum component.

Four selected acoustic biomarkers are angle-encoded across four qubits and processed using trainable RY/RZ rotations with CNOT ring entanglement.

Quantum models:
- Variational Quantum Classifier (VQC)
- Fidelity-Kernel Quantum SVM (QSVM)

Execution currently uses PennyLane's default.qubit simulator.

## Key Features

- One integrated assessment workflow
- Voice, Gait, Handwriting and EEG support
- Patient feature-input workspace
- Missing-modality support
- Hybrid quantum-classical Voice pathway
- Validation-weighted multimodal fusion
- Explainable modality contributions
- Unified final assessment report
- Light and dark interface
- Modular architecture

## Technology Stack

- Python
- NumPy
- Pandas
- SciPy
- scikit-learn
- PennyLane
- MNE-Python
- Flask
- HTML
- CSS
- JavaScript
- Joblib

## Running Locally

Install dependencies:

    pip install -r requirements.txt

Start the application:

    python app.py

Open:

    http://127.0.0.1:5000

## Repository Structure

    app.py          Flask application
    qml_platform/   Prediction and multimodal fusion logic
    models/         Trained modality models
    results/        Validation reports and feature tables
    scripts/        Training and evaluation scripts
    static/         Frontend JavaScript and CSS
    templates/      Flask HTML templates
    data/           Small Parkinson's research datasets

## Research Scope

QuantumMed is a research screening and decision-support prototype, not a standalone clinical diagnostic system.

The current modality datasets originate from independent research cohorts rather than paired measurements from the same individuals. Therefore, the system uses decision-level late fusion rather than artificial patient-level multimodal fusion.

The final Pattern Index is not a calibrated disease probability.

Future work includes paired multimodal cohort validation, prospective clinical evaluation, and raw-signal acquisition adapters.

## Team

ThunderStars

Smart India Hackathon 2026
Problem Statement ID: 26139

---

Four biomedical signals. Hybrid quantum-classical intelligence. One explainable assessment.
