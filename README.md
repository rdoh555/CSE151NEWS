# CSE151 News EDA and Analysis

This repository branch contains exploratory data analysis (EDA) for a news dataset and potential plans for further preprocessing and feature engineering.

## Project Overview

The dataset appears clean, with no missing values. We have conducted preliminary EDA to understand the data distribution and characteristics, particularly focusing on text lengths and label distribution. This project will proceed through a few stages, each adding insights and features incrementally.

## Data Exploration Steps

### Data Import and Initial Observation

1. Cloned the dataset repository:
   ```bash
   !git clone https://github.com/ikale1234/CSE151NEWS.git
   ```

2. Imported the dataset and examined the columns:
   - **title**: News article title.
   - **text**: Full news article content.
   - **label**: Binary label indicating fake (0) or real (1) news.

### Dataset Information

- **Total records**: 8,117
- **Columns**: 4 (Unnamed ID, Title, Text, Label)
- **No Missing Values**

### Key Data Observations

- **Label Distribution**: Even split between classes, visualized using `sns.countplot`.
- **Title and Text Length**: Added new features `title_length` and `text_length` to assess the distribution of title and text lengths.
- **Word Count in Titles**: Calculated word count for each title and found a diverse range of title lengths.

## Future Directions

### Additional Features for Textual Analysis

We plan to consider additional metadata and thematic analysis, though thematic analysis might be complex. Potential features we could explore include:
- **Sentiment Analysis**: Assessing the tone of the text.
- **Topic Modeling**: Exploring topics within news texts to see if certain themes are prevalent in fake or real news.
- **Named Entity Recognition**: Extracting entities (people, places, organizations) mentioned in the text to see if specific entities are associated with particular labels.

### Feature Engineering

Currently, we are only brainstorming feature ideas and creating small demos for these features. Full preprocessing will be tackled in the next milestone (MS3). Here’s a list of possible features:
- **Text-Based Features**: Sentence count, average word length, and lexical diversity.
- **Readability Scores**: Flesch-Kincaid or similar readability scores, which could offer insights into language complexity.

*Note: The README will continue to be updated to inform graders and collaborators of our thought process and approach.*
