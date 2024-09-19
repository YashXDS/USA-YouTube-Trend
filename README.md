#📊 YouTube Trending Analysis

Welcome to the YouTube Trending Analysis project! This project explores trends in YouTube videos using data visualization techniques to gain insights into popular content. The dataset used includes various metrics like views, likes, dislikes, and more for YouTube videos. In this project, we analyze video titles, visual patterns, and other numerical attributes to uncover what drives video popularity.



#🧰 Libraries & Dependencies
Before we begin, let's import the essential libraries used in the project.

python
Copy code
import pandas as pd
import numpy as np
import matplotlib as mpl
from matplotlib import pyplot as plt
import seaborn as sns

import warnings
from collections import Counter
import datetime
import wordcloud
import json
We use libraries like pandas, seaborn, matplotlib, and wordcloud for data analysis and visualization, which allow us to create beautiful visual insights.

#📂 Dataset
The dataset used in this analysis is the US_videos.csv file containing trending YouTube videos. We handle missing data and enhance the dataset for better visualizations by applying configurations to the plots for improved aesthetics.

python
Copy code
df = pd.read_csv("your_path.csv")
🎨 Configuration for Stunning Visuals
We've customized several configurations to make our visualizations clear, colorful, and engaging:

python
Copy code
PLOT_COLORS = ["#268bd2", "#0052CC", "#FF5722", "#b58900", "#003f5c"]
pd.options.display.float_format = '{:.2f}'.format
sns.set(style="ticks")
plt.rc('figure', figsize=(8, 5), dpi=100)
plt.rc('axes', labelpad=20, facecolor="#ffffff", linewidth=0.4, grid=True, labelsize=14)
# More visualization settings...
📈 Data Visualizations
Here are some of the key visualizations that we created to analyze trending YouTube videos.

1. Title Contains Capitalized Words?
We explore how many video titles contain at least one capitalized word:

python
Copy code
df["contains_capitalized"] = df["title"].apply(contains_capitalized_word)

value_counts = df["contains_capitalized"].value_counts().to_dict()
fig, ax = plt.subplots()
_ = ax.pie([value_counts[False], value_counts[True]], labels=['No', 'Yes'], 
           colors=['#003f5c', '#ffa600'], startangle=45)
_ = ax.axis('equal')
_ = ax.set_title('Title Contains Capitalized Word?')
plt.show()

2. Title Length Distribution
The distribution of video title lengths provides insights into title optimization strategies used by content creators.

python
Copy code
df["title_length"] = df["title"].apply(lambda x: len(x))

fig, ax = plt.subplots()
_ = sns.distplot(df["title_length"], kde=False, rug=False, color=PLOT_COLORS[4])
_ = ax.set(xlabel="Title Length", ylabel="No. of videos")
plt.show()

3. Views vs. Title Length
Is there a relationship between the length of the title and the number of views? Let’s visualize:

python
Copy code
fig, ax = plt.subplots()
_ = ax.scatter(x=df['views'], y=df['title_length'], color=PLOT_COLORS[2])
_ = ax.set(xlabel="Views", ylabel="Title Length")
plt.show()

4. Heatmap of Numeric Features Correlation
The heatmap allows us to explore the correlation between different numerical features such as views, likes, dislikes, and comment counts.

python
Copy code
fig, ax = plt.subplots(figsize=(10,6))
heatmap = sns.heatmap(df[numeric_cols].corr(), annot=True)
plt.show()

5. Word Cloud of Video Titles
This word cloud provides a creative visualization of the most common words used in the titles of trending YouTube videos:

python
Copy code
title_words = list(df["title"].apply(lambda x: x.split()))
wc = wordcloud.WordCloud(width=1200, height=500, background_color="white").generate(" ".join(title_words))
plt.figure(figsize=(15,10))
plt.imshow(wc, interpolation='bilinear')
plt.axis("off")
plt.show()

#💡 Key Insights
Capitalized Titles: Video titles with capitalized words might influence viewer attention.
Title Length: Short and concise titles tend to perform better.
Feature Correlations: There are interesting correlations between various numerical features, such as views and likes.
Word Frequency: Certain keywords dominate YouTube video titles.
🚀 Getting Started
Clone the repository:
bash
Copy code
git clone https://github.com/YourUsername/Youtube-Trending-Analysis.git
Install required dependencies:
bash
Copy code
pip install -r requirements.txt
Run the analysis:
bash
Copy code
python analysis.py

#🤝 Contributing
We welcome contributions! Feel free to submit issues, fork the repo, and make pull requests. Let’s build together!

#🌟 Acknowledgments
Special thanks to the open-source community for providing wonderful tools like pandas, seaborn, and matplotlib that make data visualization beautiful.
