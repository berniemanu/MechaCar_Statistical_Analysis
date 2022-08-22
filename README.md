# MechaCar_Statistical_Analysis:

A few weeks after starting his new role, Jeremy is approached by upper management about a special project. AutosRUs’ newest prototype, the MechaCar, is suffering from production troubles that are blocking the manufacturing team’s progress. AutosRUs’ upper management has called on Jeremy and the data analytics team to review the production data for insights that may help the manufacturing team.

In this challenge, you’ll help Jeremy and the data analytics team do the following:

* Perform multiple linear regression analysis to identify which variables in the dataset predict the mpg of MechaCar prototypes
* Collect summary statistics on the pounds per square inch (PSI) of the suspension coils from the manufacturing lots
* Run t-tests to determine if the manufacturing lots are statistically different from the mean population
* Design a statistical study to compare vehicle performance of the MechaCar vehicles against vehicles from other manufacturers. For each statistical analysis, you’ll write a summary interpretation of the findings.

## Deliverable 1: Linear Regression to Predict MPG
Steps 1 - 4: Download, import and read MechaCar_mpg.csv file as a dataframe.
![image](https://user-images.githubusercontent.com/104685001/185924817-0489f52c-658e-40f4-a058-fbe81f5ae899.png)

Step 5: Perform linear regression using the lm() function. In the lm() function, pass in all six variables (i.e., columns), and add the dataframe you created in Step 4 as the data parameter.
![image](https://user-images.githubusercontent.com/104685001/185925091-d36aa81d-9d43-4b80-a283-21f07c743d5a.png)

Step 6-7: Using the summary() function, determine the p-value and the r-squared value for the linear regression model. 
Save your MechaCarChallenge.RScript file to your GitHub repository.

![image](https://user-images.githubusercontent.com/104685001/185925362-98f74755-3b57-4efc-9a4f-8ddd32ed5eb1.png)

## Summary:
**1. Which variables/coefficients provided a non-random amount of variance to the mpg values in the dataset?**
Vehicle length and ground clearance are statistically likely to provide non-random amounts of variance to the model. They also have a significant impact on miles per gallon on the MechaCar prototype. Conversely, the vehicle weight, spoiler angle, and All Wheel Drive (AWD) have p-Values that indicate a random amount of variance with the dataset

**2. Is the slope of the linear model considered to be zero? Why or why not?**
The p-Value for this model, p-Value: 5.35e-11, is much smaller than the assumed significance level of 0.05%. This indicates there is sufficient evidence to reject our null hypothesis, which further indcates that the slope of this linear model is not zero.

**3. Does this linear model predict mpg of MechaCar prototypes effectively? Why or why not?**
If we remove the less impactful independent variables (vehicle weight, spoiler angle, and All Wheel Drive), the predictability does decrease, but not drastically: the r-squared value falls from 0.7149 to 0.674.

## Deliverable 2: Create Visualizations for the Trip Analysis
Steps 1-2: Download, import and read in the Suspension_Coil.csv file as a table.
![image](https://user-images.githubusercontent.com/104685001/185927577-8970bbd7-db8c-48b1-b7b1-412bcb3e7ee2.png)

Step 3: Write an RScript that creates a total_summary dataframe using the summarize() function to get the mean, median, variance, and standard deviation of the suspension coil’s PSI column
![image](https://user-images.githubusercontent.com/104685001/185927752-80b7723f-1d61-4e20-a408-59eaf673dcf7.png)

Steps 4-5: Write an RScript that creates a lot_summary dataframe using the group_by() and the summarize() functions to group each manufacturing lot by the mean, median, variance, and standard deviation of the suspension coil’s PSI column. Save your MechaCarChallenge.RScript file to your GitHub repository.
![image](https://user-images.githubusercontent.com/104685001/185927901-3f3d9ce6-9e07-421b-9bdb-7c57ef8520f3.png)

### Summary:
**The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not?**
For the entire population of the production lot, the variance of the coils is 62.29 PSI, which is < 100 PSI variance requirement.
Lot 1 and Lot 2 are well within the 100 PSI variance requirement; with variances of 0.98 and 7.47 respectively. 

However, it is Lot 3 that is showing much larger variance in performance and consistency, with a variance of 170.29. 
It is Lot 3 that is disproportionately causing the variance at the full lot level.

![image](https://user-images.githubusercontent.com/104685001/185928709-c1745f73-01b0-4eca-b7a2-a52024950856.png)

## Deliverable 3: T-Tests on Suspension Coils
Step 1: In your MechaCarChallenge.RScript, write an RScript using the t.test() function to determine if the PSI across all manufacturing lots is statistically different from the population mean of 1,500 pounds per square inch. Save your MechaCarChallenge.RScript file to your GitHub repository.

Steps 2-3: Next, write three more RScripts in your MechaCarChallenge.RScript using the t.test() function and its subset() argument to determine if the PSI for each manufacturing lot is statistically different from the population mean of 1,500 pounds per square inch.

## Written Summary:
![image](https://user-images.githubusercontent.com/104685001/185936951-e0a15b63-5ba2-49c4-9e95-69b72916ddaf.png)
The true mean of the sample is 1498.78, with a p-Value of 0.06, which is higher than the common significance level of 0.05, there is NOT enough evidence to support rejecting the null hypothesis. Also, the mean of all three of these manufacturing lots is statistically similar to the presumed population mean of 1500.

Next looking at each individual lots:

Lot 1 sample actually has the true sample mean of 1500, with a p-Value of 1, clearly we cannot reject (i.e. accept) the null hypothesis that there is no statistical difference between the observed sample mean and the presumed population mean (1500).
Lot 2 has essentially the same outcome with a sample mean of 1500.02, a p-Value of 0.61; the null hypothesis cannot be rejected, and the sample mean and the population mean of 1500 are statistically similar.
However, for Lot 3, the sample mean is 1496.14 and the p-Value is 0.04, which is lower than the common significance level of 0.05. All indicating to reject the null hypothesis that this sample mean and the presumed population mean are not statistically different.
![image](https://user-images.githubusercontent.com/104685001/185937152-a2303bce-bf14-4f6b-a378-5174f50de4af.png)

![image](https://user-images.githubusercontent.com/104685001/185937245-40f47ec5-d5c4-4568-ac42-9a602fa498b8.png)

![image](https://user-images.githubusercontent.com/104685001/185937323-08aa6c6a-efde-4ed4-94fa-8711e5f63fcb.png)

## Deliverable 4: Design a Study Comparing the MechaCar to the Competition
Using your knowledge of R, design a statistical study to compare performance of the MechaCar vehicles against performance of vehicles from other manufacturers.

First we need to collect data on MechaCar and its comparable models across several different manufacturers over the last 5 years.
This involves answering the following questions:

1. What are the competitions' comparable models to be involved in the study?
2. Of the entire population in question1, which models are closely competing with MechaCar's cars?
3. What are current customer demands that affects the sales price?

### Metrics
Collecting data for comparable models across all major manufacturers for past 3 years for the following metrics:

* Safety Feature Rating: Independent Variable
* Current Price (Selling): Dependent Variable
* Drive Package : Independent Variable
* Engine (Electric, Hybrid, Gasoline / Conventional): Independent Variable
* Resale Value: Independent Variable
* Average Annual Cost of ownership (Maintenance): Independent Variable
* MPG (Gasoline Efficiency): Independent Variable

### Hypothesis: Null and Alternative
Null Hypothesis (Ho): MechaCar is priced correctly based on its performance of key factors for its genre.
Alternative Hypothesis (Ha): MechaCar is NOT priced correctly based on performance of key factors for its genre.

### Statistical Tests
A multiple linear regression would be used to determine the factors that have the highest correlation/predictability with the list selling price (dependent variable); which combination has the greatest impact on price (it may be all of them!)
