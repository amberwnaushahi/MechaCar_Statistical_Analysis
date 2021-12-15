![image](https://github.com/amberwnaushahi/MechaCar_Statistical_Analysis/blob/main/Images/AutoRUs.png)

# MechaCar_Statistical_Analysis

## Backgorund 

AutosRUs’ newest prototype, the MechaCar, is suffering from production troubles that are blocking the manufacturing team’s progress. AutosRUs’ upper management has called on Jeremy and the data analytics team to review the production data for insights that may help the manufacturing team.

The Deliverables include:

* Multiple linear regression analysis to identify which variables in the dataset predict the mpg of MechaCar prototypes
* Summary statistics on the pounds per square inch (PSI) of the suspension coils from the manufacturing lots
* Run t-tests to determine if the manufacturing lots are statistically different from the mean population
* Design a statistical study to compare vehicle performance of the MechaCar vehicles against vehicles from other manufacturers. For each statistical analysis, we will write a summary interpretation of the findings.

Data Source: MechaCar_mpg.csv and Suspension_Coil.csv
Data Tools: tidyverse, dplyr, ggplot2 and MechaCarChallenge.RScript
Software: RStudio and R

## Deliverable 1: Linear Regression to Predict MPG

![image](https://github.com/amberwnaushahi/MechaCar_Statistical_Analysis/blob/main/Images/Linear%20Regression.PNG)

### Statistical Summary:

From the above output we can see that:

The vehicle length and vehicle ground clearance have a significant impact on miles per gallon on the MechaCar prototype. Conversely, the vehicle weight, spoiler angle, and All Wheel Drive (AWD) have p-Values that indicate a random amount of variance with the dataset.

The p-Value for this model, p-Value: 5.35e-11, is much smaller than the assumed significance level of 0.05% which indicates there is sufficient evidence to reject our null hypothesis, which further indcates that the slope of this linear model is not zero.

This linear model has an r-squared value of 0.7149, which means that approximately 71% of all mpg predictions will be determined by this model. Relatively speaking, this multiple regression model does predict mpg of MechaCar prototypes effectively.

If we remove the less impactful independent variables (vehicle weight, spoiler angle, and All Wheel Drive), the predictability does decrease, but not drastically: the r-squared value falls from 0.7149 to 0.674.

### Deliverable 2: Summary Statistics on Suspension Coils

The MechaCar Suspension_Coil.csv dataset contains the weight capacities of multiple suspension coils were tested to determine if the manufacturing process is consistent across production lots. This dataset was used to create a total summary dataframe that has the mean, median, variance, and standard deviation of the PSI for all manufacturing lots and antoher dataframe containing the same information for each manufacturing lot. 

![image](https://github.com/amberwnaushahi/MechaCar_Statistical_Analysis/blob/main/Images/summary_table_lots.PNG)

![image](https://github.com/amberwnaushahi/MechaCar_Statistical_Analysis/blob/main/Images/lot_summary.PNG)

The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. When looking at the entire population of the production lot, the variance of the coils is 62.29 PSI, which is well within the 100 PSI variance requirement.

Individually, Lot 1 and Lot 2 are well within the 100 PSI variance requirement; with variances of 0.98 and 7.47 respectively. However, it is Lot 3 that is showing a much larger variance in performance and consistency, with a variance of 170.29. It is Lot 3 that is disproportionately causing the variance at the total lot level.

This very simple boxplot illustrates the differences between the lots:

![image](https://github.com/amberwnaushahi/MechaCar_Statistical_Analysis/blob/main/Images/lot_box_plot.PNG)

## Deliverable 3: t-Tests on Suspension Coils

We performed t-tests to determine if all manufacturing lots and each lot individually are statistically different from the population mean of 1,500 pounds per square inch.

![image](https://github.com/amberwnaushahi/MechaCar_Statistical_Analysis/blob/main/Images/all%20lot%20sample-t-test.PNG)

A review of the results of the T-test for the suspension coils across all manufacturing lots shows that they are not statistically different from the population mean. With a p-Value of 0.06, which is higher than the common significance level of 0.05, there is NOT enough evidence to support rejecting the null hypothesis. 

Next looking at each individual lots:

![image](https://github.com/amberwnaushahi/MechaCar_Statistical_Analysis/blob/main/Images/individual%20lot%20sample-t-test.PNG)

* Lot 1 shows it is not statistically different from the population mean, and the p-value is not low enough (1) for us to reject the null hypothesis.

* Lot 2 shows it is not statistically different from the population mean, and the p-value is not low enough (0.6072) for us to reject the null hypothesis.

* Lot 3 shows it is slightly statistically different from the population mean, and the p-value is just low enough (0.04168) for us to REJECT the NULL hypothesis. This lot may be need to be re-evaluated, and other varibles can be reviewed to understand the variance.

## Deliverable 4: Study Design: MechaCar vs Competition

This study would involve collecting data on MechaCar and its comparable models across several different manufacturers over the last 3 years.

1) The first step would be to identify comparable models of the competitors to include in the study
2) Next, metrics would need to be identified and collected for the comparable models. These could include:

* Safety Feature Rating: Independent Variable
* Selling Price: Dependent Variable
* Drive Package : Independent Variable
* Engine Type (Electric, Hybrid, Gasoline / Conventional): Independent Variable
* Average Annual Maintenance Costs: Independent Variable
* MPG (Gasoline Efficiency): Independent Variable

3) Hypothesis: Null and Alternative
After determining which factors are key for the MechaCar's genre, we can establish the null and alternative hypothesis:

* Null Hypothesis (Ho): MechaCar is priced correctly based on its performance of key factors for its genre.
* Alternative Hypothesis (Ha): MechaCar is NOT priced correctly based on performance of key factors for its genre.

4) Conduct our Statistical Tests and Analysis
A multiple linear regression would be used to determine the factors that have the highest correlation/predictability with the selling price (dependent variable), along with assessing which combination has the greatest impact on price
