# Practical Application 2: What drives the price of a car?

## 🗃️ Folders & Files

🔗 Github Reposiroty: https://github.com/sgmlai/berkmlai/tree/main/PA_2

🔗 data: https://github.com/sgmlai/berkmlai/tree/main/PA_2/data

🔗 images: https://github.com/sgmlai/berkmlai/tree/main/PA_2/images

🔗 README.md: https://github.com/sgmlai/berkmlai/blob/main/PA_2/README.md

🔗 Jupyter Notebook PA_2: https://github.com/sgmlai/berkmlai/blob/main/PA_2/prompt_II.ipynb

##### Overview: In this application, you will explore a dataset from Kaggle. The original dataset contained information on 3 million used cars. The provided dataset contains information on 426K cars to ensure speed of processing. Your goal is to understand what factors make a car more or less expensive. As a result of your analysis, you should provide clear recommendations to your client -- a used car dealership -- as to what consumers value in a used car.

###### The exercise follows problem solving approach using CRISP-DM Framework

#### 💡Business Understanding

**User Car sales market drives good revenue, approx $2B in Minnesota alone which is good news for auto dealers, creates more jobs in the industry and benefits state as well in form of taxes.**

**While the markets are booming, Its important for the Used car dealers to constantly refresh their inventory to keep their business growing.**

**So, the key factors that contributes to the price of the car helps delaers to stay competetive with inventory and become valuable in the marketplace.**

**Let's dive into dataset and analyze the key factors that can help us solve the problem.**

#### 📊 Data Understanding

**To understand and prepare the data, we need certain domain knowledge to select the features that contributes more to determine the car price.**
**Several factors influence a car's price, including the vehicle's condition, mileage, age, features, and market demand.**
**Other important considerations include engine performance, fuel efficiency, and the presence of advanced safety and technology features.** 

##### Key Features Affecting Car Price:

1. Vehicle Condition:
    A car's overall condition, including interior and exterior wear and tear, as well as any mechanical issues, significantly impacts its value.
 
2. Mileage and Age:
    Older cars generally depreciate faster, and higher mileage can also reduce a car's resale value. 

3. Car Options and Features:
The presence of desirable features like leather upholstery, advanced infotainment systems, and safety packages can increase a car's price. 

4. Market Demand:
Popular and in-demand car models tend to hold their value better and may even command higher prices. 

5. Engine Performance and Fuel Efficiency:
Cars with powerful engines and good fuel economy are often more attractive to buyers and may command higher prices. 

6. Safety and Technology:
Cars with advanced safety features like driver-assistance systems and modern technology features like smartphone integration are in demand and can increase value. 

7. Maintenance History:
A car with a good maintenance history can be more attractive to buyers, as it suggests that the vehicle has been well-maintained and is in good condition. 

8. Accident and Repair Records:
A car's history of accidents and repairs can negatively impact its value. 

9. Brand Reputation:
Certain car brands are known for their reliability and longevity, which can influence their perceived value and impact their price. 

**Based on the above information, using it as domain knowledge, Let's examine, refine our dataset and prepare it.**

#### 🧹 Data Preparation

**Drop features that does not add much importance in driving the price of the car**
1. ID
2. VIN
3. PaintColor
4. Region - This is almost duplicate information to state feature.

**Engineer new features based on existing Features**

   a. Year feature can be used to create Age of the vehicle.
   
   b. Cylinders feature can be converted into numeric by extracting number from the string and handle the NaN with default values.
   
**Handle missing data based on the samples**
   a. drop missing rows if the percentage is very small.
   b. Impute missing data. Used Lookup based Imputer in this case.
   
      Lookup Imputer,Why?? Mostly, A specific model from manufactures comes with certain number of cylinder, unless remodeled by customer.
      1. We created dictionary lookup on Manufacturer and Model, We imputed the missing data in number of Cylinders feature.
      2. We created lookup based on vehicle_age, Manufacturer and Model, and imputed Vehicle Condition feature.
      3. We created lookup based on State, Manufacturer and Model, and imputed Vehicle Drive feature.
      4. We created lookup based on Manufacturer and Model, and imputed Vehicle type feature.
      5. We created lookup based on Manufacturer and type, and imputed Vehicle size feature.      

**Use appropriate encoding methods o convert the categorical into numerical features.**

   a. OneHot Encoding - One Hot encoding suits well for this dataset for all categorical features.

**Once the above steps are completed, 

    Drop Year column as Age of vehicle provides similar information.
    
    Drop Model column as well because it has high cardinality and adds too many dimesion when encoded using OHE**

**Filter rows with price != 0 and price > 250,000. The condition of the vehicle is shown good and Excellent but zero price did not make sense.**

#### 🤖 Modeling

Consider: Linear Regression, Lasso and Ridge models for this Regression problem in predicting continuous variable, price of car.

Lasso and Ridge models have performed better than Linear Regression.

We have performed cross validation and hyper tuning of alphas using Gridsearch CV. The best params are below.

Best parameters for Lasso: {'alpha': 0.01}


Best parameters for Ridge: {'alpha': 0.1}

#### ✂️ Evaluation

1. We can select Lasso model for our evaluation and presentation.

2. The dataset is inventory of used cars with prices. The price is not consistent for given manufacturer, model and condition. So, We may need to go back to Data Understanding and clean the data more and evaluate the dataset with Lasso Regression model as final step.

3. As the data is very random, the best way is to split them according to state and Top 10 Manufacturers and perform analysis.

4. Model is biased towards the higher priced cars and choosing those features with more omprtance in driving price. Go back to data cleaning and remove the outliers.

#### Findings

#### After revisiting the data and removing the outlier brands and priced vehicles. Below is the report for our used car dealers.

1. Vehicle Age and Odometer are prime contributors for customer choice. Newer Vehicles can drive more customers.
2. Trucks, Sedans, SUVs are most commonly used vehicle types. These vehicle type are important to be in dealer inventory.
3. Ford, Cheverolet, Jeep brands have good average price and very affordable to customers.
4. State of California car delaers can have little inventory of vintage and expensive brands as well.

Overall, Ford, Cheverolet & Jeep branded Trucks, Sedans and SUVs which are newer and in good condition is the prime focus in our inventory.






