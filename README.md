# MechaCar_Statistical_Analysis

## Project Overview
This project involves the use of statistics and hypothesis testing to analyze a series of datasets from the automotive industry.\
All of the statistical analysis and visualizations is written in the R programming language.

## Resources
- Data Source: [MechaCar_mpg.csv](https://github.com/Diana7e/MechaCar_Statistical_Analysis/blob/e7ed08e1f8578e5ffea23c4043962f72abdbcc87/challenge/MechaCar_mpg.csv), [Suspension_Coil.csv](https://github.com/Diana7e/MechaCar_Statistical_Analysis/blob/e7ed08e1f8578e5ffea23c4043962f72abdbcc87/challenge/Suspension_Coil.csv)
- Software: RStudio  

<br>

## Linear Regression to Predict MPG

<p align="center">
    <img src="https://github.com/Diana7e/MechaCar_Statistical_Analysis/blob/7cc5a0f76c809e69d7b8f0c9edc563008d4bdb13/challenge/Liner%20Regression%20to%20predict%20MPG.png"> 
</p>

- In the summary output, each Pr(>|t|) value represents the probability that each coefficient contributes a random amount of variance to the linear model. According to our results vehicle length and ground clearance (and Intercept) provide a non-random amount of variance to the linear model of mpg.

- According to the results, the multi linear model is:

<p align="center">
    <img src="https://github.com/Diana7e/MechaCar_Statistical_Analysis/blob/7cc5a0f76c809e69d7b8f0c9edc563008d4bdb13/challenge/mpg%20mlt.png"> 
</p>

Approximated to:


<p align="center">
    <img src="https://github.com/Diana7e/MechaCar_Statistical_Analysis/blob/7cc5a0f76c809e69d7b8f0c9edc563008d4bdb13/challenge/mpg%20apr.png"> 
</p>

So the slope of the linear model is not considered to be zero.

- R-square is 0.71 so 71% of the variations in mpg can be explained by changes in the vehicle length, the vehicle weight, the spoiler angle, the drivetrain and the ground clearance. We can consider this linear model as fairly efficient to predict mpg of MechaCar prototypes.

<br>

## Summary Statistics on Suspension Coils

<p align="center">
    <img src="https://github.com/Diana7e/MechaCar_Statistical_Analysis/blob/7cc5a0f76c809e69d7b8f0c9edc563008d4bdb13/challenge/mmv.png"><br>All manufacturing lots 
</p>
<p align="center">
    <img src="https://github.com/Diana7e/MechaCar_Statistical_Analysis/blob/7cc5a0f76c809e69d7b8f0c9edc563008d4bdb13/challenge/lot.png"><br>By each manufacturing lot
</p>

The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch.\
The design specs are respected for all manufacturing lots in total with a global variance of 62.3 psi.\
On the lot level, Lot 1 and Lot 2 are into specs with respectively variances of 0.98 and 7.5 psi. The Lot 3 is out of specs with a variance of 170.3 psi.

<br>

## T-Tests on Suspension Coils

### T-Test all manufacturing lots against the population mean

<p align="center">
    <img src="https://github.com/Diana7e/MechaCar_Statistical_Analysis/blob/7cc5a0f76c809e69d7b8f0c9edc563008d4bdb13/challenge/t_test%20all.png"> 
</p>

Assuming our significance level is the common 0.05 percent, our p-value of 0.069 is above the significance level. Therefore, we do not have sufficient evidence to reject the null hypothesis, and we can state that the PSI across all manufacturing lots is statiscally similar to the population mean of 1498.78 psi.

### T-Tests each manufacturing lot against the population mean

#### Lot1

<p align="center">
    <img src="https://github.com/Diana7e/MechaCar_Statistical_Analysis/blob/7cc5a0f76c809e69d7b8f0c9edc563008d4bdb13/challenge/t_test%20lot1.png"> 
</p>

Here the p-value is below the significance level of 0.05 percent, so we can reject the null hypothesis and conclude that the PSI across the Lot 1 is statistically different from the population mean.

<br>

#### Lot2 and Lot3

<p align="center">
    <img src="https://github.com/Diana7e/MechaCar_Statistical_Analysis/blob/7cc5a0f76c809e69d7b8f0c9edc563008d4bdb13/challenge/lot%202.png"><br>Lot 2  
</p>
<p align="center">
    <img src="https://github.com/Diana7e/MechaCar_Statistical_Analysis/blob/7cc5a0f76c809e69d7b8f0c9edc563008d4bdb13/challenge/lot3.png"><br>Lot3
</p>

Here Lot2 p-values are above the significance level, so we can conclude that the PSI for Lot2  is statistically similar to the population mean.

<br>

## Study Design: MechaCar vs Competition
To compare the performance of the MechaCar prototype against the vehicles from the competition, we will perform a statistical analysis based on the following metrics: 
- the "0 to 60 mph" time,
- the braking distance,
- the fuel economy (mpg),
- the Power,
- the safety rating.

In our case the null hypothesis would be: each performance metrics is statistically similar between the MechaCar prototype and all vehicle from the other manufacturers.

We would use a one-way ANOVA test. This test is used to compare the means of a continuous numerical variable across a number of groups.\
So in this analysis we would compare the means for each metric across the different manufacturers.

To perform the test, we would need data of MechaCar vehicles and its competition, all gathered in a single dataframe where each metric is a column.\
The data could be scraped from vehicle data APIs such as [scrapinghub.com/data-api-vehicle](https://www.scrapinghub.com/data-api-vehicle/) or [carqueryapi.com](https://www.carqueryapi.com/).