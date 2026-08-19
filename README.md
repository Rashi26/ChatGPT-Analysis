# ChatGPT User Reviews Analysis

An exploratory data analysis project on ChatGPT user reviews, focusing on user ratings, sentiment, recurring issues, review behavior, and changes in feedback over time.

## Overview

User reviews provide valuable insight into how people experience a product. This project analyzes a large collection of ChatGPT reviews to understand overall user sentiment, identify recurring issues in negative feedback, and explore how user feedback changes over time.

The analysis combines **rating-based sentiment**, **text-based sentiment analysis**, **keyword and phrase analysis**, and **time-series analysis**.

## Objectives

The project focuses on three main questions:

- **Sentiment Analysis** — How are user reviews distributed across positive, neutral, and negative sentiment?
- **Issue Identification** — What recurring words and phrases appear in negative reviews?
- **Time-Series Analysis** — How does the volume and sentiment of reviews change over time?

Additional text analysis is used to compare the language of positive, neutral, and negative reviews.

## Dataset

The dataset contains **196,727 reviews** with the following fields:

| Column | Description |
|---|---|
| `Review Id` | Unique identifier for each review |
| `Review` | Written user review |
| `Ratings` | User rating |
| `Review Date` | Date and time when the review was submitted |

The dataset initially contains 196,727 records, with a small number of missing review texts.

During preprocessing, missing reviews are removed and duplicate review texts are dropped. This results in **125,495 unique reviews** used for the analysis.

## Analysis Workflow

### 1. Data Import & Overview

The dataset is loaded and inspected to understand its structure, data types, and completeness.

### 2. Data Cleaning & Preprocessing

The preprocessing steps include:

- Removing reviews with missing text
- Removing duplicate review texts
- Converting review dates to datetime format
- Converting review text to lowercase
- Removing non-alphabetic characters for text analysis
- Creating monthly review periods
- Calculating review word counts

### 3. Exploratory Data Analysis

The analysis explores:

- Distribution of user ratings
- Distribution of review lengths
- Overall characteristics of user feedback

### 4. Sentiment Analysis

Two approaches are used to analyze sentiment.

#### Rating-Based Sentiment

Reviews are grouped according to their ratings:

- **Positive:** 4–5 stars
- **Neutral:** 3 stars
- **Negative:** 1–2 stars

#### Text-Based Sentiment

**TextBlob** is used to calculate text polarity and subjectivity.

Polarity provides a measure of how positive or negative the language is, while subjectivity provides an indication of how opinion-oriented the review text is.

> Rating-based sentiment and text-based sentiment are treated as separate measures because they capture different aspects of user feedback.

### 5. Issue Identification

Negative reviews are examined using:

- Word-frequency analysis
- Bigrams and trigrams
- Word clouds

This helps identify recurring topics and phrases associated with negative user experiences.

### 6. Time-Series Analysis

Reviews are aggregated by month and sentiment category to examine how user feedback changes over time.

This can help identify periods with unusual changes in review volume or sentiment that may warrant further investigation.

### 7. Deeper Text Analysis

The project also compares language across sentiment groups using:

- Polarity
- Subjectivity
- Positive-review bigrams
- Negative-review bigrams
- Sentiment-specific word clouds

This provides a more detailed view of the language associated with satisfaction and frustration.

## Key Takeaways

The analysis provides a framework for understanding ChatGPT user feedback from multiple perspectives:

- Ratings provide a direct measure of user satisfaction.
- Review text provides additional context behind those ratings.
- Negative-review phrases can highlight recurring areas of friction.
- Review length helps distinguish short feedback from more detailed user experiences.
- Monthly trends can reveal changes in feedback volume and sentiment.
- Comparing positive and negative language can help distinguish potential drivers of satisfaction from recurring problems.

## Tools & Technologies

- **Python**
- **Pandas** — Data manipulation and analysis
- **NumPy** — Numerical operations
- **Matplotlib** — Data visualization
- **Seaborn** — Statistical visualization
- **TextBlob** — Text sentiment analysis
- **Regular Expressions (`re`)** — Text preprocessing
- **WordCloud** — Text visualization

## Project Structure

```text
.
├── ChatGPT_Analysis2.ipynb
├── chatgpt_reviews.csv
└── README.md
