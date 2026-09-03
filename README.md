# LLM Financial Sentiment Analysis

## Overview

This project explores the use of Large Language Models (LLMs) for financial sentiment analysis of earnings call transcripts.

Completed as part of my MSc Business Analytics at University College London (UCL), the project investigates whether LLMs can reliably support investment decision-making by identifying financially relevant information and classifying the sentiment expressed in corporate earnings calls.

The research evaluates both the potential and the limitations of using LLMs within financial analysis workflows, with particular attention to model accuracy, consistency, scalability, and the role of human oversight.

## Project Objectives

The project investigates several key questions:

- Can LLMs distinguish financially relevant information from irrelevant content in earnings call transcripts?
- Can LLMs accurately classify financial sentiment from strongly negative to strongly positive?
- Are there consistent patterns in LLM classification errors?
- Does model performance vary depending on the company being analysed?
- How does the choice of LLM affect accuracy, processing time, and cost?
- Can prompt engineering improve model performance?
- What risks and limitations should be considered when using LLMs for financial decision support?

## Methodology

Earnings call transcripts from two publicly listed companies, Uber Technologies and Blackstone, were processed and divided into paragraph-level textual segments.

The project used human-annotated sentiment labels as the ground truth for evaluating LLM predictions.

Two Large Language Models were evaluated:

- OpenAI GPT-3.5
- DeepSeek-V2

The evaluation followed a two-stage classification process:

1. **Relevance Classification**  
   Determine whether each transcript segment contains financially relevant information.

2. **Sentiment Classification**  
   Relevant segments are classified using a five-point sentiment scale:

   `-2` Strongly Negative  
   `-1` Negative  
   `0` Neutral  
   `+1` Positive  
   `+2` Strongly Positive

Model performance was evaluated using quantitative metrics and qualitative error analysis.

## Key Findings

The analysis identified several important limitations in using LLMs for financial sentiment analysis.

### Relevance Detection

GPT-3.5 initially achieved approximately **79% accuracy** in distinguishing relevant from irrelevant transcript segments.

A recurring source of error involved procedural statements containing names of analysts or financial institutions. After refining the prompt to address this pattern, relevance classification accuracy increased to approximately **89%**.

### Sentiment Intensity

Fine-grained sentiment classification proved substantially more difficult.

GPT-3.5 achieved approximately **51% exact-match accuracy** across the five sentiment categories.

Many errors were "off-by-one" classifications, where the model identified the correct sentiment direction but underestimated or overestimated its intensity.

### Optimism Bias

The analysis identified a tendency for the LLM to assign more positive sentiment than the human annotations.

This was particularly important in earnings calls, where executives may communicate negative information using cautious or optimistic language.

### Company-Specific Performance

Model performance varied between Uber and Blackstone transcripts, suggesting that differences in financial terminology, business complexity, and communication style can affect LLM sentiment classification.

## Interactive Dashboard

An interactive dashboard was developed to support model evaluation and explore classification errors.

The dashboard enables users to investigate:

- Confusion matrices
- Individual misclassified transcript segments
- Sentiment classification patterns
- Word clouds of misclassified instances
- Model runtime and performance comparisons

The dashboard also demonstrates how a human-in-the-loop system could support analysts when reviewing LLM-generated sentiment classifications.

## Technologies & Tools

- Python
- Pandas
- NumPy
- Scikit-learn
- OpenAI API
- DeepSeek API
- Streamlit
- Matplotlib
- Seaborn
- NLP preprocessing
- Prompt engineering
- LLM evaluation

## Business Implications

The results suggest that fully automated LLM-based financial sentiment analysis still presents important accuracy and reliability challenges.

A **hybrid human-AI approach** may therefore be more appropriate, where LLMs perform initial classification and analysis while human analysts review ambiguous or high-impact cases.

This approach can combine the scalability and speed of LLMs with the contextual understanding and judgement of financial analysts.

## Repository Structure

### `Code/`
Contains the Jupyter notebooks used for LLM-based sentiment classification and evaluation, including separate experiments for Uber and Blackstone using OpenAI and DeepSeek models.

### `Dashboard/`
Contains the Streamlit dashboard implementation and the setup/execution guide for running the interactive evaluation dashboard.

### `Data/`
Contains the datasets used throughout the project, including Uber, Blackstone, and combined datasets used for model evaluation.

### `Results/`
Contains the final model evaluation outputs, including sentiment misclassification results used for error analysis.

### `requirements.txt`
Lists the main Python packages required to run the project.

## Academic Context

**Programme:** MSc Business Analytics  
**Institution:** University College London (UCL)  
**Academic Year:** 2024–2025  
**Project Type:** MSc Business Analytics Consultancy Project / Dissertation

## Author

Sara Alyahya
