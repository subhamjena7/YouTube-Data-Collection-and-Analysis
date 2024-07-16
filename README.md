# YouTube Data Collection and Analysis with Python

This project focuses on collecting data about the trending videos on YouTube to analyze and understand what makes a video trend on the platform. The data is collected using the YouTube Data API, and the analysis is performed using Python.

## Getting Started

To collect data from YouTube, you need to set up an API. Follow these steps to get started:

1. Go to [Google Cloud Console](https://console.cloud.google.com/).
2. Click on the project drop-down at the top, then “New Project”.
3. Enter a project name and click “Create”.
4. In the Google Cloud Console, navigate to “APIs & Services” > “Library”.
5. Search for “YouTube Data API v3” and click on it.
6. Click “Enable”.
7. Go to “APIs & Services” > “Credentials”.
8. Click “+ CREATE CREDENTIALS” and select “API key”.
9. Copy the generated API key.

## Project Steps

1. **Data Collection:**
   - We collect data about the top 200 trending videos on YouTube in India.
   - Using the YouTube Data API, we fetch details such as title, description, published date, channel information, tags, duration, definition, captions, and various engagement metrics like views, likes, and comments.
   - The collected data is compiled into a list, converted into a pandas DataFrame, and saved to a CSV file named `trending_videos.csv`.

2. **Data Preprocessing:**
   - Convert the `published_at` column to a datetime format.
   - Further process the `tags` column if needed.

3. **Distribution Analysis:**
   - Analyze the distribution of views, likes, and comments of all the videos.
   - Histograms show right-skewed distributions, with most videos having lower counts and a few videos having very high counts.

4. **Correlation Analysis:**
   - Examine the correlation between likes, views, and comments.
   - A heatmap confirms strong positive correlations between these metrics.

5. **Category Analysis:**
   - Collect and analyze category names along with the category ID.
   - Create a bar chart to show the number of trending videos by category.
   - Entertainment, Music, People & Blogs, and Comedy categories have the highest number of trending videos.

6. **Engagement Metrics by Category:**
   - Analyze average engagement metrics (views, likes, comments) by category.
   - Sports has the highest average view counts, likes, and comments, followed by Gaming.

7. **Video Duration Analysis:**
   - Convert video duration from ISO 8601 format to seconds using the `isodate` library.
   - Categorize videos into different duration ranges (0-5 minutes, 5-10 minutes, 10-20 minutes, 20-60 minutes, and 60-120 minutes).
   - Analyze engagement metrics within specific length intervals.
   - A scatter plot shows a slight positive correlation between video length and view count.

8. **Tags Analysis:**
   - Analyze the relationship between views and the number of tags used in the video.
   - A scatter plot shows a very weak relationship, suggesting minimal impact of tags on view count.

9. **Publishing Time Analysis:**
   - Examine the impact of the time a video is posted on its views.
   - Most videos are published between 4 AM to 5 AM and 11 AM to 4 PM.
   - There is a very weak negative relationship between publish hour and view count, suggesting minimal impact on engagement metrics.

## Conclusion

Based on the analysis, here are some recommendations for making a video trend on YouTube:
- Encourage viewers to like and comment on videos to boost engagement metrics.
- Aim to create long videos (60-120 minutes) for higher engagement, especially for categories like Gaming and Entertainment.
- Schedule video uploads around peak times (11 AM – 4 PM) to maximize initial views and engagement.

## Dependencies

Ensure you have the following Python packages installed:
- `pandas`
- `requests`
- `isodate`
- `matplotlib`
- `seaborn`

## Usage

To run the script, ensure you have your API key and necessary dependencies installed. Then execute the script to start collecting and analyzing YouTube trending video data.

```bash
python youtube_data_collection.py
