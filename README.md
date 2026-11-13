
# Python Final Project
This is my final project for my Python Course. Below is the link to the dataset I will be using. You can also find the notebook that I used for my analysis in the files attached to this reposetory. 

## Sleep Health and Lifestyle
https://www.kaggle.com/datasets/uom190346a/sleep-health-and-lifestyle-dataset

The Sleep Health and Lifestyle Dataset covers a wide range of variables related to sleep and daily habits. It includes gender, age, occupation, sleep duration, quality of sleep, physical activity level, stress levels, BMI category, blood pressure, heart rate, daily steps, and any recorded sleep disorders.

There are many things that go into a successful life. Sleep, exercise, and work are just a few of these. Throughout the analysis, I was able to find some interesting patterns regarding Occupation, Quality of Sleep, and even the surprising correlation between Stress and the quality of your sleep.

## Summary of Analysis
### Ingesting the Dataset
This was a pretty straightforward process. First, I downloaded the zip file from Kaggle, then extracted the csv to load into Google Colab, where I used the Padas `read_csv()` method to turn the csv into a workable dataframe. 

### Cleaning the DataFrame
Using the `.info()` and `.describe()` method, we can see if we have any missing values or anything that stands out in the data. Using these methods, I was able to determine only a single column with inconsistencies: Sleep Disorder. Rows where an individual did not have a sleep order contained a null value. So, to make out analysis and visualization easier in the future, I filled the null values with the string 'None' using the `fillna` method.

### Data Manipulation
This is where I started seeing some interesting patters. Using `groupby`, `agg`, and conditions, I was able to determine the following:
1) On average, Engineers get the longest and best quality sleep (about 8 Hours a night with an average score of 8.4 out of 10), while Sales Representatives get the worst sleep (about 6 Hours a night with an average score of 4 out of 10).

2) Women tend to sleep slightly longer and better than men, averaging 7.2 hours of sleep with a score of 7.7, compared to a Mans 7 with a score of 7.

3) When looking at all ages, teachers were in the bottom half of sleep quality. When filtered to ages less than 30, they ranked 2nd highest in sleep quality, right behind doctors. This tells us that younger teachers tend to sleep better on average compared to other aged teachers.

### Data Visualizations
<img width="489" height="512" alt="image" src="https://github.com/user-attachments/assets/c3d45d8f-614f-4b66-ba29-86301461af88" />

This line graph shows the relationship between stress and quality of sleep. We can see that individuals who reported a low amount of stress also tended to report better sleep. As individuals reported higher amounts of stress, their sleep score decreased. 



<img width="996" height="682" alt="image" src="https://github.com/user-attachments/assets/1f7083e8-ad38-425a-bba9-79af0d8c78b6" />

The count plot shows us the count of individuals, categorized by their occupation, who have specific sleep disorders. We can see a few professions who tend to have certain disorders from this graph; Almost all doctors reported having no sleep disorders, while a large majority of nurses reported Sleep Apnea. 



<img width="580" height="587" alt="image" src="https://github.com/user-attachments/assets/ed7d744f-cc5c-4708-a29f-1ce3bdca1d57" />

Finally, the bar plot above shows us the average daily steps of each occupation. Nurses, Doctors, and Lawyers all have relatively active schedules, resulting in a higher average step count of around 7 to 8000. Sales Reps, however, average about 3000 steps a day, reflecting a less active schedule. 



### Statistical Analysis
Because so many factors go into how well we sleep, it made the most sense to do a correlation heat map between applicable variables. 

<img width="675" height="575" alt="image" src="https://github.com/user-attachments/assets/e90fe11d-68e8-4de1-9d1e-e42b6bb38bf4" />

From the heat map, we can see the strongest correlations come from the Stress Level category, which shows a very strong negative correlation between stress and sleep quality and duration. As stress increases, sleep quality and duration decrease drastically. 

