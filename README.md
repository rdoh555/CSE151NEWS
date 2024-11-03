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
- **Word Count in Texts**: Applied same metric as above but to article text in particular.

## Future Directions

### Additional Features for Textual Analysis

To enhance our model’s predictive power, we aim to explore features that could capture meaningful differences in language use between real and fake news. Potential features include:

1. **TF-IDF Analysis**: 
   - We plan to implement Term Frequency-Inverse Document Frequency (TF-IDF) as a way to identify unique words that are more or less likely to appear in real vs. fake news. TF-IDF will help highlight words that are characteristic of each label, shedding light on the linguistic patterns specific to fake or real news articles.
   - This analysis could allow us to identify terms with high discriminatory power, which could serve as predictive indicators in later modeling stages.

2. **Unique Words Analysis**:
   - Using the TF-IDF scores, we will identify words that are uniquely associated with each label (e.g., words that frequently appear in fake news but rarely in real news, and vice versa).
   - This approach will help us understand which words may be predictive of the news label and could inform additional feature engineering efforts or provide a basis for sentiment analysis.
   
We plan to consider additional metadata and thematic analysis, though thematic analysis might be complex. Potential features we could explore include:
- **Sentiment Analysis**: Assessing the tone of the text.
- **Topic Modeling**: Exploring topics within news texts to see if certain themes are prevalent in fake or real news.
- **Named Entity Recognition**: Extracting entities (people, places, organizations) mentioned in the text to see if specific entities are associated with particular labels.

### Preprocessing

In order to create features from our text data, we need to perform preprocessing steps to make sure our features can pick up patterns while removing as much noise as possible here are some preprocessing steps:
- **Removing Punctuation**: Using Regular expressions or other filters we can take out punctuation to make sure our features can accurately find words without punctuation causing any confusion.
- **Removing Stop Words**: Using an imort like NLTK we can remove stop words, which are words that carry little significance, this can make the words that do remain more significant for our model predictions.
- **Tokenization**: Depending on some of our features Tokenization through either (stemmatization or lemmatization) would allow us to make our text easier to analyze. We will then map each token to a unique integer in order for the data to be suitable for machine learning.
- **Padding**: Machine learning algorithms need an input shape that is consistent, and since the word sequences in our dataset vary in length, we need to add padding to our data (or potentially truncate). This will change the variable length sequences to a fixed length.
- **Embeddings**: Using our integer mapped tokens, we can create embeddings for each available token. These embeddings are vectors of a chosen length (n) that are randomly initialized. These will be n*(token size) new parameters that are trained over time, and essentially act as a way to "give meaning" to each token. In most modern libaries this is usually a quick step one can add to the beginning of their model, but since it is technically a change in the representation of our input data before we start training we will include it here.


### Feature Engineering

Currently, we are only brainstorming feature ideas and creating small demos for these features. Full preprocessing will be tackled in the next milestone (MS3). Here’s a list of possible features:
- **Text-Based Features**: Sentence count, average word length, and lexical diversity.
- **Readability Scores**: Flesch-Kincaid or similar readability scores, which could offer insights into language complexity.

*Note: The README will continue to be updated to inform graders and collaborators of our thought process and approach.*
