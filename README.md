# YouTube Trend Analysis

A data analysis project focused on understanding trends in YouTube videos. This project uses Python for data manipulation, exploration, and visualization. It demonstrates key skills in handling large datasets, performing feature engineering, and creating insightful visualizations using libraries such as **Pandas**, **Matplotlib**, **Seaborn**, and **WordCloud**.

## Project Overview

This project analyzes the trends in a dataset of YouTube videos, primarily focusing on:
- Detecting patterns in video titles (e.g., the use of capitalized words)
- Investigating the relationship between video title lengths and other attributes (such as views)
- Visualizing correlations between numerical features
- Creating word clouds to analyze the most frequently used words in video titles

## Libraries & Tools

- **Pandas**: For data manipulation and analysis.
- **NumPy**: For efficient numerical computations.
- **Matplotlib & Seaborn**: For creating static, animated, and interactive visualizations.
- **WordCloud**: For generating word cloud visualizations.
- **Datetime**: To handle time-based features.
- **Collections (Counter)**: To handle frequency analysis of words.
- **XAMPP** (optional): Used in earlier projects for MySQL database hosting if further enhancements are added.

## Dataset

The dataset used for analysis is a CSV file of YouTube trending videos, which includes various attributes such as:
- **Title**
- **Description**
- **Views**
- **Likes**
- **Dislikes**
- **Comment Count**
- **Publish Time**

In this analysis, we focus on video title properties and their correlation with other attributes like views and engagement.

## Setup

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/youtube-trend-analysis.git

2. Install the required Python packages:

   ```bash
   pip install -r requirements.txt
   ```
   
3. Update the path to the dataset (US_videos.csv) in the script as needed:

   ```python

    df = pd.read_csv("path/to/your/dataset/US_videos.csv")
   
4. Run the analysis script:

   ```bash
   python analysis.py
   ```
   
## Features & Analysis

1. Data Visualization & Exploration
   
- **Capitalized Words in Titles**: Analysis of whether YouTube video titles contain capitalized words, using pie charts to visualize the results.

- **Title Length Distribution**: A distribution plot showing the frequency of video titles by their length.


- **Scatter Plot (Views vs Title Length)**: A scatter plot to visualize the relationship between video views and the length of the title.


2. Correlation Heatmap
   
A correlation heatmap between numerical features like views, likes, dislikes, and comment count to understand the relationships between these features.


3. Word Cloud
   
A word cloud visualization showing the most frequently used words in video titles, generated from the dataset.


4. Feature Engineering
   
- **Capitalization Detection**: A custom function is used to detect if a title contains fully capitalized words, and this information is used for further analysis.
- **Title Length**: Title length is calculated and compared with various metrics like views and engagement.
  
## How It Works

-**Data Loading and Preparation**: The dataset is loaded using Pandas, and missing values in the "description" column are handled by filling them with empty strings.
- **Capitalization Detection**: The dataset is enhanced with a new feature that identifies whether the video title contains capitalized words.
- **Visualization**: The following visualizations are created using Matplotlib and Seaborn:
  
Pie chart of capitalized words in titles.
Distribution plot of title lengths.
Scatter plot showing the relationship between views and title length.
Correlation heatmap of numerical features.
Word cloud of the most common words in video titles.

## Customization

- **PLOT_COLORS**: You can modify the PLOT_COLORS variable to customize the colors of your visualizations.
- **Heatmap Options**: You can adjust the heatmap's colormap by modifying the Seaborn settings in the script.
- **WordCloud Settings**: Customize the word cloud generation by adjusting parameters such as width, height, and colormap.
  
## Future Enhancements

- **Sentiment Analysis**: Analyze the sentiment of video descriptions to find trends in viewer engagement.
- **Engagement Prediction**: Use machine learning models to predict the engagement of videos based on title length, capitalization, and other factors.
- **Temporal Analysis**: Explore how video trends evolve over time by analyzing the publishing date and time.
