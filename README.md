#   MechaCar_Statistical_Analysis: R Programming
##  Overview of Project
A few weeks after starting his new role, Jeremy is approached by upper management about a special project. AutosRUs’ newest prototype, the MechaCar, is suffering from production troubles that are blocking the manufacturing team’s progress. AutosRUs’ upper management has called on Jeremy and the data analytics team to review the production data for insights that may help the manufacturing team. In this challenge, you’ll help Jeremy and the data analytics team do the following:

• Perform multiple linear regression analysis to identify which variables in the dataset predict the mpg of MechaCar prototypes

• Collect summary statistics on the pounds per square inch (PSI) of the suspension coils from the manufacturing lots

• Run t-tests to determine if the manufacturing lots are statistically different from the mean population

• Design a statistical study to compare vehicle performance of the MechaCar vehicles against vehicles from other manufacturers. For each statistical analysis, you’ll write a summary interpretation of the findings.

##  Reports:
This new assignment consists of three technical analysis deliverables and a proposal for further statistical study. You’ll submit the following:

Linear Regression to Predict MPG
Summary Statistics on Suspension Coils
T-Test on Suspension Coils
Design a Study Comparing the MechaCar to the Competition

##  Resources:

• Data Source: MechaCar_mpg.csv and Suspension_Coil.csv, Stack Overflow

• Data Tools: tidyverse, dplyr, and MechaCarChallenge.RScript.

• Software: RStudio and R

1. Linear Regression to Predict MPG
Requirements:

The MechaCar_mpg.csv dataset contains mpg test results for 50 prototype MechaCars. The MechaCar prototypes were produced using multiple design specifications to identify ideal vehicle performance. Multiple metrics, such as vehicle length, vehicle weight, spoiler angle, drivetrain, and ground clearance, were collected for each vehicle. Using your knowledge of R, you’ll design a linear model that predicts the mpg of MechaCar prototypes using several variables from the MechaCar_mpg.csv file. To Deliver.

• The MechaCar_mpg.csv file is imported and read into a dataframe

• An RScript is written for a linear regression model to be performed on all six variables

• An RScript is written to create the statistical summary of the linear regression model with the intended p-values

• There is a summary that addresses all three questions

Results on Deliverable: Resulting Model

mpg = (6.267)vehicle_length + (0.0012)vehicle_weight + (0.0688)spoiler_angle + (3.546)ground_clearance + (-3.411)AWD + (-104.0)

 ![image 1](https://github.com/jhansolo33/MechaCar_Statistical_Analysis/assets/119264589/83aa3dfd-e46c-4700-a19a-8e86beb8bfc8)



##  Summary: 

A:The vehicle length, and vehicle ground clearance are statistically likely to provide non-random amounts of variance to the model. That is to say, the vehicle length and vehicle ground clearance have a significant impact on miles per gallon on the MechaCar prototype. Conversely, the vehicle weight, spoiler angle, and All Wheel Drive (AWD) have p-Values that indicate a random amount of variance with the dataset.

B:The p-Value for this model, p-Value: 5.35e-11, is much smaller than the assumed significance level of 0.05%. This indicates there is sufficient evidence to reject our null hypothesis, which further indcates that the slope of this linear model is not zero.

C:This linear model has an r-squared value of 0.7149, which means that approximately 71% of all mpg predictions will be determined by this model. Relatively speaking, his multiple regression model does predict mpg of MechaCar prototypes effectively.

D:If we remove the less impactful independent variables (vehicle weight, spoiler angle, and All Wheel Drive), the predictability does decrease, but not drastically: the r-squared value falls from 0.7149 to 0.674.

##  2. Summary Statistics on Suspension Coils
Requirements:

The MechaCar Suspension_Coil.csv dataset contains the results from multiple production lots. In this dataset, the weight capacities of multiple suspension coils were tested to determine if the manufacturing process is consistent across production lots. Using your knowledge of R, you’ll create a summary statistics table to show: • The suspension coil’s PSI continuous variable across all manufacturing lots • The following PSI metrics for each lot: mean, median, variance, and standard deviation.

##  Technical Analysis:
A:Download the Suspension_Coil.csv file, and place it in the active directory for your R session.
B:In your MechaCarChallenge.RScript, import and read in the Suspension_Coil.csv file as a table.
C:Write an RScript that creates a total_summary dataframe using the summarize() function to get the mean, median, variance, and standard deviation of the suspension coil’s PSI column. The dataframe:

 ![image 2](https://github.com/jhansolo33/MechaCar_Statistical_Analysis/assets/119264589/b59c1ffe-97d4-4eb2-a9aa-12bc723e9ad2)


D:Write an RScript that creates a lot_summary dataframe using the group_by() and the summarize() functions to group each manufacturing lot by the mean, median, variance, and standard deviation of the suspension coil’s PSI column. The lot_summary dataframe:

 ![image 5](https://github.com/jhansolo33/MechaCar_Statistical_Analysis/assets/119264589/157520ae-7b1a-4130-8c51-4613aee94831)
![image 6](https://github.com/jhansolo33/MechaCar_Statistical_Analysis/assets/119264589/5f6408d4-b5f4-4eed-824e-573037412da4)


The Suspension Coil dataset provided for the MechaCar contains the results of testing the weight capacities of multiple suspension coils from multiple production lots to determine consistency. At first all manufacturing lots:

# ![image 7](https://github.com/jhansolo33/MechaCar_Statistical_Analysis/assets/119264589/1747f4b1-470a-4731-b819-570af59db78a)


Diving a little deeper into each of the 3 lots:

#  ![image 8](https://github.com/jhansolo33/MechaCar_Statistical_Analysis/assets/119264589/cda07c3b-3931-4928-b4cd-3744581bd4ca)


Having the knowledge that the design specifications for the MechaCar suspension coils mandate that the variance of the suspension coils cannot exceed 100 pounds per square inch (PSI) . Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not? When looking at the entire population of the production lot, the variance of the coils is 62.29 PSI, which is well within the 100 PSI variance requirement. Similarly, but significantly more consistent, Lot 1 and Lot 2 are well within the 100 PSI variance requirement; with variances of 0.98 and 7.47 respectively. However, it is Lot 3 that is showing much larger variance in performance and consistency, with a variance of 170.29. It is Lot 3 that is disproportionately causing the variance at the full lot level. 

##  3. t-Tests on Suspension Coils:

Requirements: Using your knowledge of R, perform t-tests to determine if all manufacturing lots and each lot individually are statistically different from the population mean of 1,500 pounds per square inch.

Technical Analysis:
A:In your MechaCarChallenge.RScript, write an RScript using the t.test() function to determine if the PSI across all manufacturing lots is statistically different from the population mean of 1,500 pounds per square inch.
B:Next, write three more RScripts in your MechaCarChallenge.RScript using the t.test() function and its subset() argument to determine if the PSI for each manufacturing lot is statistically different from the population mean of 1,500 pounds per square inch.

C:
• An RScript is written for t-test that compares all manufacturing lots against mean PSI of the population

• An RScript is written for three t-tests that compare each manufacturing lot against mean PSI of the population

• There is a summary of the t-test results across all manufacturing lots and for each lot

The next step is to conduct a t-test on the suspension coil data to determine whether there is a statistical difference between the mean of this provided sample dataset and a hypothesized, potential population dataset. Using the presumed population mean of 1500, we find the following: Summary of the t-test results across all manufacturing lots:

# ![t-test1](https://github.com/jhansolo33/MechaCar_Statistical_Analysis/assets/119264589/a96a5cbc-921c-4349-aadf-e8df8a43fb41)


From here we can see the true mean of the sample is 1498.78, which we also saw in the summary statistics above. With a p-Value of 0.06, which is higher than the common significance level of 0.05, there is NOT enough evidence to support rejecting the null hypothesis. That is to say, the mean of all three of these manufacturing lots is statistically similar to the presumed population mean of 1500.

# ![t-test2](https://github.com/jhansolo33/MechaCar_Statistical_Analysis/assets/119264589/44619238-0fea-4273-9588-5242326357a3)


Next looking at the individual lots:

Lot 1 - sample actually has the true sample mean of 1500, again as we saw in the summary statistics above. With a p-Value of 1, clearly we cannot reject (i.e. accept) the null hypothesis that there is no statistical difference between the observed sample mean and the presumed population mean (1500).
Lot 2 - has essentially the same outcome with a sample mean of 1500.02, a p-Value of 0.61; the null hypothesis cannot be rejected, and the sample mean and the population mean of 1500 are statistically similar.
Lot 3 -  Is a different result. Here the sample mean is 1496.14 and the p-Value is 0.04, which is lower than the common significance level of 0.05. All indicating to reject the null hypothesis that this sample mean and the presumed population mean are not statistically different. Something went awry in Lot 3's production cycle. The process needs to be checked for system fails and the suspension coils from this lot need to be inspected to remove those not meeting quality criteria.

##  Study Design: MechaCar vs Competition
Requirements: Using your knowledge of R, design a statistical study to compare performance of the MechaCar vehicles against performance of vehicles from other manufacturers. The statistical study design has the following:

• A metric to be tested is mentioned

• A null hypothesis or an alternative hypothesis is described

• A statistical test is described to test the hypothesis

The exercise includes collecting data on MechaCar and its comparable models across several different manufacturers over the last 3 years.

• What are the competitions' comparable models,

• Which cars will MechaCar be competing with head-to-head? which cars will be included in the study?

• Which factors will look at the study to determine the relevant to selling price?

Metrics
Collecting data for comparable models across all major manufacturers for past 3 years for the following metrics:

• Safety Feature Rating: Independent Variable

• Current Price (Selling): Dependent Variable

• Drive Package : Independent Variable

• Engine (Electric, Hybrid, Gasoline / Conventional): Independent Variable

• Resale Value: Independent Variable

• Average Annual Cost of ownership (Maintenance): Independent Variable

• MPG (Gasoline Efficiency): Independent Variable

Hypothesis: Null and Alternative
After determining which factors are key for the MechaCar's genre:

• Null Hypothesis (Ho): MechaCar is priced correctly based on its performance of key factors for its genre.

• Alternative Hypothesis (Ha): MechaCar is NOT priced correctly based on performance of key factors for its genre.

##Statistical Tests:

A multiple linear regression is used to determine the factors that have the highest correlation/predictability with the list selling price (dependent variable); which combination has the greatest impact on price.






