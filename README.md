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

