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
