# Linear-Regression-FDA-Project
Using Linear Regression to predict wind turbine power output from wind speeds.

The objectives of this project are; 
1 Perform linear regression on the dataset.
2 Explain what this shows.
3 Predict wind speed power output from wind speed values.

I started by importing the dataset into my Jupyter Notebook.  Then I took a look at the datatypes, the dataset
itself and I plotted the 500 (x,y) values on a simple plot.  The plot seems to indicate that no power is produced at
very low or very high wind speeds.  The turbines start to produce power at 10 km/h approx and levels off producing peak 
power at about 18km/h.

I then decided to study some sources to make myself familiar with the purpose and elements of linear regression.  I went back
to FDA Lecture 4, Datasets and Simulation, where we examined this particular dataset before.  In that lecture we used the input u,
wind speed, in an equation to figure out the value of P_u, power produced by wind turbine.  In the csv file which I imported and converted
into a dataframe, dfpower, I created a plot which resembles the one from Lecture 4. 

The next step was to revise Lecture 9, Linear Regression.  This lecture emphasised polynomial functions, coefficients and polyfit and I revised all 
of this and went through the Jupyter Notebooks accompanying the lecture before I proceeded much further.

The final bit of preparation I did was to go through the linear regression lesson in Real Python and the same lesson in w3schools.  I find Real
Python very helpful particularly the video lessons, although there were none for this topic the written article was very informative.  I found it
helpful to look at the approach on the w3schools site also because they show what the end result of each step should look like.

Using the information in Real Python I imported LinearRegression from SKlearn.  I fit the speed and power data to this model and was able to calculate
the coefficient of determination, the y intercept and the slope of the line of regression.  I used this to calculate predicted y values and then plotted
this line of regression against my original x and y data.  

My next plan is to go through the steps emphasised in lecture 9 and then try to form some conclusions on the data and assess its predictive value.
I first used polyfit to find the relationship between the x and y variables.  To use polyfit x must be a 1D vector so I converted x to an np.array called speed_data_array.
this will return an array which includes the coefficients; aka the intercept of y axis, bo and the slope of regression line, b1.  These are the same figures as
I produced using LinearRegression.  Numpy polyfit plots the original data and the bestfit regression line and again the plot is the same as the one produced using LinearRegression. 
Calculating the cost of the line does much of the same work as we have done.  The equation is: Cost(m,c)= Σ(yi - mxi-c)² where m is the slope and c is the constant or y intercept.  This method produces the m and c values.

The Pearson correlation coefficient measures the linear relationship between two variables.  Positive correlations imply that as x increases so does y, 
negative correlations imply that if x increases, y decreases. The Pearson's r value implies a strong positive correlation between wind speed and turbine power output.
I also tested the correlation between the two variables using Spearman's Rho and Kendall's Tau and found there is a high correlation coefficient between wind speed, x, and power production, y.  The values range from 0.73 on the Kendall's Tau to the highest correlation 0.85 on the Pearson's r.

I cited a faq, from a wind energy company Enerpower, which shows how to interpret the data. The illustrated data shows that no power is produced until the wind speed reaches 8 mph, at 20-25 mph it has reached peak production and levels off. Winds above 20 mph on my plot seem to indicate the best speed for producing power. Higher wind speeds do not produce more power.

Having analysed this data we have the following information to help predict a y value from an x value and to interpret the data:
Coefficient of determination: 0.7289360258564073 
Intercept: 13.89990263 slope: 4.91759567 
Pearson's r = 0.8537775037188595 

I next used the equation of the line to predict y for 10 selected values of x.  I created a smaller sample called x1 and used it to predict the y values.
Equation:  y1 = mx1 + c, x1 = speed, y1 = power.  The subsequent plot shows the positive correlation between values of x1, the sample of speed variables 
and y1, the sample of turbine power output.  The arrangement of the points shows a positive correlation but it must also take into account that there is a horizontal section before 0-7mph and after 20mph. There must be a windspeed of 7+ for power to be produced and speeds over 20mph do not produce more power.

The last topic I examined was to see if Polynomial Regression produces a better correlation between speed and power.
I used the numpy method to make a polynomial regression model, plotting 500 points in the sample from the first x value, 0, to the last x value, 25.
I plotted the original data set and the polynomial line of regression.  Then I calculated the coefficient of determination of the data using the polyfit method to find the coefficient of determination or R².  
 
This is a sample of 500 elements where the wind speed (x with values from 0 to 25) produces a power output (y) the y variable is dependent on the x variable. Using the Linear Regression model I found the coefficient of determination to be 0.7289360258564073, this shows a high positive correlation. Using the Polynomial Regression model I found the coefficient of determination to be 0.8796883953739737, this indicates that polynomial regression modelling is more effective as it shows a higher correlation between x and y. The coefficient of determination or R² is the proportion of the variance for a dependent variable that may be explained by the influence of independent variable(s). The closer the coefficient of determination is to 1 the better the fit, because it indicates the sum of squared residuals (SSR) is 0 which is perfect.

Results

Established a relationship between wind speed and power output using LinearRegression and Polyfit.
Explained the purpose of Linear Regression and what my data shows.
Used values of x to predict values of y.
Created a Polynomial Regression model to show that this is a better method of analysing the data.

