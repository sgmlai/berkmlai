# The README provides information about the data in the dataset and explains the steps taken to perform the analysis.


\## Practical Application 1: Will the Customer Accept the Coupon?



\## 🗃️ Folders \& Files



🔗 Github Reposiroty: https://github.com/sgmlai/berkmlai/tree/main/PA_1



🔗 data: https://github.com/sgmlai/berkmlai/tree/main/PA_1/data



🔗 README.md: https://github.com/sgmlai/berkmlai/blob/main/PA_1/README.md


🔗 Jupyter Notebook: https://github.com/sgmlai/berkmlai/blob/main/PA_1/prompt.ipynb



\#####################################################################################################

Steps followed to answer "Will the Customer Accept the Coupon?"

Step 1: Read \& Describe the data to inspect and see if any missing information in the dataset.
Step 2: Format and cleanse the data by handling missing values and converting Categorical to numerical data etc..
Step 3: Observe the data correlation using heat map to understand the tight correlation between features.
Step 4: Visualize the data using Seaborn and Matplotlib to reveal information
Step 5: Answer the question based on the visualizations and correlation drawn from above.
######################################################################################################

Python Libraries used

1. Pandas
2. Matplotlib
3. Seaborn

\#######################################################################################################

Findings

Found some interesting information from the analysis to answer the question "Will the Customer Accept the Coupon?"

1. Drivers who are alone OR driving with friends have accepted most coupons.
2. Majority of the coupons are sent to drivers on Sunny day.
3. Carry out, Coffee House \& Cheaper restaurant coupons stood out with more acceptance.
4. Age groups (21,26,31) have accepted most Carry out, Coffee House \& Cheaper restaurant coupons
5. Also, Age groups (21,26,31) showed habits of visiting Carry out, Coffee House \& Cheaper restaurant 1~3 times per week

From my Analysis, Younger age groups travelling alone or with friends have higher Carry out, Coffee House \& Cheaper restaurant coupon acceptance rate and the rest are less likely to accept coupons.
#######################################################################################################

Next steps

There are other dimensions that can be added to the analysis, like..
a. time at which most coupons are accepted.
b. Travel time to reach business location.
c. Income
d. Destination etc..



Adding these would lead to different conclusions and may provide other insights too..



Combining these features might also lead to insight into characteristics of drivers those who have not accepted the coupons.



\#######################################################################################################

Dataset Detailed Description

Will the Customer Accept the Coupon?

Context

Imagine driving through town and a coupon is delivered to your cell phone for a restaurant near where you are driving. Would you accept that coupon and take a short detour to the restaurant? Would you accept the coupon but use it on a subsequent trip? Would you ignore the coupon entirely? What if the coupon was for a bar instead of a restaurant? What about a coffee house? Would you accept a bar coupon with a minor passenger in the car? What about if it was just you and your partner in the car? Would weather impact the rate of acceptance? What about the time of day?

Obviously, proximity to the business is a factor on whether the coupon is delivered to the driver or not, but what are the factors that determine whether a driver accepts the coupon once it is delivered to them? How would you determine whether a driver is likely to accept a coupon?

Overview

The goal of this project is to use what you know about visualizations and probability distributions to distinguish between customers who accepted a driving coupon versus those that did not.

Data

This data comes to us from the UCI Machine Learning repository and was collected via a survey on Amazon Mechanical Turk. The survey describes different driving scenarios including the destination, current time, weather, passenger, etc., and then ask the person whether he will accept the coupon if he is the driver. Answers that the user will drive there ‘right away’ or ‘later before the coupon expires’ are labeled as ‘Y = 1’ and answers ‘no, I do not want the coupon’ are labeled as ‘Y = 0’. There are five different types of coupons -- less expensive restaurants (under  20), coffee houses, carry out \& take away, bar, and more expensive restaurants (
20 - $50).



Data Description

Keep in mind that these values mentioned below are average values.

The attributes of this data set include:

User attributes

Gender: male, female
Age: below 21, 21 to 25, 26 to 30, etc.
Marital Status: single, married partner, unmarried partner, or widowed
Number of children: 0, 1, or more than 1
Education: high school, bachelors degree, associates degree, or graduate degree
Occupation: architecture \& engineering, business \& financial, etc.
Annual income: less than $12500, $12500 - $24999, $25000 - $37499, etc.
Number of times that he/she goes to a bar: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
Number of times that he/she buys takeaway food: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
Number of times that he/she goes to a coffee house: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
Number of times that he/she eats at a restaurant with average expense less than $20 per person: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
Number of times that he/she eats at a restaurant with average expense $20 - $50 per person: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
Contextual attributes

Driving destination: home, work, or no urgent destination
Location of user, coupon and destination: we provide a map to show the geographical location of the user, destination, and the venue, and we mark the distance between each two places with time of driving. The user can see whether the venue is in the same direction as the destination.
Weather: sunny, rainy, or snowy
Temperature: 30F, 55F, or 80F
Time: 10AM, 2PM, or 6PM
Passenger: alone, partner, kid(s), or friend(s)
Coupon attributes

time before it expires: 2 hours or one day

\#####################################################################################################

