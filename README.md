# Mobile App Funnel Analysis and A/A/B Test

[open in nbviewer](https://nbviewer.org/github/Eydelkind/Mob_app_funnel_ab_test/blob/main/mobile_app_funnel_ab_test.ipynb)

This notebook contains the full analysis with interactive visualizations (Plotly).

## Project Overview
This project analyzes user behavior in a grocery store mobile application.

The analysis had two main goals:
1. study the product event funnel;
2. evaluate the results of an A/A/B test.

In the experiment, users in the experimental group were shown a version of the app with modified fonts. The task was to determine whether this UI change affected user behavior compared with the control groups. :contentReference[oaicite:1]{index=1}

## Dataset
The dataset contains event logs with the following fields:
- `EventName`
- `DeviceIDHash`
- `EventTimestamp`
- `ExpId`

After preprocessing and duplicate removal, the working dataset contained **243,713 events**. :contentReference[oaicite:2]{index=2}

## Tools
- Python
- pandas
- numpy
- matplotlib
- seaborn
- plotly
- scipy

## What I Did

### 1. Data preprocessing
- loaded and inspected the event log;
- removed duplicates;
- renamed columns and event labels for readability;
- converted timestamps into datetime format;
- created a separate date column for analysis. :contentReference[oaicite:3]{index=3}

### 2. Data validation
- checked event distribution over time;
- found that the data for the first week was too sparse and uneven;
- excluded the underrepresented early period from the analysis to avoid distorted results. :contentReference[oaicite:4]{index=4}

### 3. Funnel analysis
- identified the main product funnel events:
  - main screen
  - offers screen
  - cart screen
  - payment successful
- excluded the tutorial event from the funnel because it did not reflect the main purchase path;
- calculated the share of users reaching each step. :contentReference[oaicite:5]{index=5}

### 4. Experiment analysis
- compared two control groups in an A/A test to verify that the experiment setup was valid;
- compared each control group with the experimental group;
- compared the combined control group with the experimental group;
- used z-tests to evaluate differences in conversion between groups at each funnel step. :contentReference[oaicite:6]{index=6}

## Key Findings

- The largest drop-off occurs between the **main screen** and the **offers screen**. :contentReference[oaicite:7]{index=7}
- About **48% of users** reach the successful payment stage. :contentReference[oaicite:8]{index=8}
- The A/A test showed **no statistically significant differences** between the two control groups. :contentReference[oaicite:9]{index=9}
- The A/B comparisons also showed **no statistically significant differences** between the experimental group and either control group, or between the experimental group and the merged control group. :contentReference[oaicite:10]{index=10}
- Final conclusion: **the font change did not have a measurable impact on user behavior** at this stage of the experiment. :contentReference[oaicite:11]{index=11}

## Business Conclusion
The tested UI change — modified fonts in the app — did not improve funnel conversion and did not significantly affect user behavior. Based on this analysis, there is no evidence that the new font design should be rolled out for product reasons alone. :contentReference[oaicite:12]{index=12}

## Project Structure
- `mobile_application_of_shop.ipynb` — full analysis in Jupyter Notebook

## Skills Demonstrated
- data cleaning and preprocessing
- event log analysis
- product funnel analysis
- A/A/B test evaluation
- statistical hypothesis testing
- data visualization
- business interpretation of analytical results
