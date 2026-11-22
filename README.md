Goal: Use machine learning to check if the model could estimate Delhi's AQI by training it on same-day pollutants data from 2015-2020.


Data: https://www.kaggle.com/datasets/rohanrao/air-quality-data-in-india 
License: CC0: Public Domain, per the Kaggle dataset page.

The data has been made publicly available by the Central Pollution Control Board: https://cpcb.nic.in/ which is the official portal of Government of India. They also have a real-time monitoring app: https://app.cpcbccr.com/AQI_India/


Note: The Delhi subset contains 1,228 rows of Delhi air quality data after removing missing values.


**Approach and Results:**

*   For this analysis, I decided to train the model on the following pollutants: benzene, toluene, xylene, along with the month, to check whether it could estimate the AQI. I left out other pollutants, which could be used to calculate the AQI, from the training data to prevent the model from calculating it directly.

*   I used a bar chart to graphically represent the mean AQI trend across the 12 months, which showed the highest average to be in the months of November and December. The lowest months were July and August (monsoon season).

*   The model's average error was 55 points, compared to the baseline average error of 96 points (the baseline guesses the median AQI for every day).

**What I Learned:**

*   I had initially used a different dataset for calculation, it suspiciously showed an average error of 0.0026, which meant that the model was estimating the AQI by calculating it using the pollutants data rather than looking at the pattern, or "data leakage". This is when I realized that the dataset and training inputs need to be changed. 

**Limitations:**

*   The dataset is small with the analysis focused only on the city of Delhi.

*   This model serves to estimate the AQI, rather than forecast it.

*  While cleaning the missing values, the data was cut down from 2,009 to 1,228.

**Acknowledgements:**

I learned Python, pandas and scikit-learn for this project with guidance from Claude (Anthropic's AI assistant), which acted as a tutor and explained concepts, helped with the code, answered questions, and helped me interpret the results. I made the modelling decisions and wrote the findings.

