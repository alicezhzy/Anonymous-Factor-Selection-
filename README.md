# Anonymous-Factor-Selection-
We want to produce two calibrations Y1 ~ f(X1...X375) and Y2 ~ f(X1...X375).
DATA:

We have provided 298 daily files, covering the 15-month period 20220104 - 20230331, for you to use in this project.
The column names of the files are:
time: timestamp specifying milliseconds from midnight. Start time is 35101000
(9:45am) and end time is 57600000 (4:00pm)
Q1: quality variable #1 - to be used as a quality flag for calibration of Y1
Q2: quality variable #2 - to be used as a quality flag for calibration of Y2
Y1: dependent variable #1 to be predicted
Y2: dependent variable #2 to be predicted
X1 to X375: 375 independent variables to be used as inputs to predict both Y1 and Y2

PROBLEM INSTRUCTIONS:

Use 2 subsets of the 375 X variables to make 2 separate calibrations for Y1 and Y2.
If Q1 is less than 1 (make the test Q1 < 0.9999 to handle floating point precision), then the row should be excluded from the calibration of Y1.
Similarly, if Q2 is less than 1, the row should be excluded from the calibration of Y2. Q1 and Q2 are used to indicate the quality of Y1 and Y2 respectively. And if they are less than 1, it means 
that Y1 or Y2 are not in a good state.
We have decided to limit the techniques used for the calibrations to either linear regression, gradient-boosted trees, or neural networks.
You can use any sub-periods of the 15-month period as in-sample or out-of-sample. You can use all the data or can sample the data.
A value of 999999 or NaN indicates a bad value so you should skip it.
You may want to skip a row if more than a certain percentage of values (50% or 70%) are bad values.
The calibration can be for the whole day (coefficient 0.15 for variable X12) or split by time of day (between 9:45 and 11:00 the coefficient for X12 is 0.12 and 0.18 between 11:00 and 14:00 and so on) - 
it's up to you but try to be reasonable when you split the day in periods (i.e. avoid having a different coefficient for each minute or each hour of the day).
We have provided you with real financial data for this project. Many times such data is less clean than the stylized data samples that you encounter in class.

You may not use lagged Y and X variables as inputs but some transformations of the X variables are ok (X7^2, X9*X23)
