*****Variables!*****
(1) race is a two-level categorical explanatory variable, 0=white and 1=black
(2) sex is a two-level categorical explanatory variable, 0=male and 1=female
(3) atty_typ_desc is a two-level categorical explanatory variable, 0=appointed and 1=hired
(4) cs_disp_less30 is a two-level categorical explanatory variable, 0=sentenced more than 30 days after arrest and 1=sentenced within 30 days after arrest
(5) judge is a categorical explanatory variable with 6 levels, which represents the different judges who passed the sentence, 0=CC3, 1=CC5, 2=CC6, 3=CC7, 4=CC8, 5=CC9
(6) age is a numerical explanatory variable
(7) Final Disposition Description is a two-level categorical response variable, 0=jail and 1=probation
*****Frequency Tables!*****
Race Frequency Table: 0=white and 1=black
Count of Each Defendant's Race
0    5267
1     599
Name: race, dtype: int64
Percentage of Each Defendant's Race
0   0.897886
1   0.102114
Name: race, dtype: float64
Sex Frequency Table: 0=male and 1=female
Count of Each Defendant's Sex
0    4282
1    1584
Name: sex, dtype: int64
Percentage of Each Defendant's Sex
0   0.729969
1   0.270031
Name: sex, dtype: float64
Attorney Type Frequency Table: 0=appointed and 1=hired
Count of Each Defendant's Attorney Type
0    1633
1    4233
Name: atty_typ_desc, dtype: int64
Percentage of Each Defendant's Attorney Type
0   0.278384
1   0.721616
Name: atty_typ_desc, dtype: float64
Whether the Sentence Was Within 30 Days of Arrest Frequency Table: 0=sentenced more than 30 days after arrest and 1=sentenced within 30 days after arrest
Count of Whether the Sentence Was Within 30 Days of Arrest
0    5575
1     291
Name: cs_disp_less30, dtype: int64
Percentage of Whether the Sentence Was Within 30 Days of Arrest
0   0.950392
1   0.049608
Name: cs_disp_less30, dtype: float64
Judge Table: 0=CC3, 1=CC5, 2=CC6, 3=CC7, 4=CC8, 5=CC9
Count of Each Court/Judge
0     877
1    1047
2     982
3     965
4    1032
5     963
Name: judge, dtype: int64
Percentage of Each Court/Judge
0   0.149506
1   0.178486
2   0.167405
3   0.164507
4   0.175929
5   0.164166
Name: judge, dtype: float64
Age Table: Numerical
Count of Each Defendant's Age
20      3
24    145
28    352
32    269
36    214

63     22
67     17
71      6
75      1
79      1
Name: age, Length: 64, dtype: int64
Percentage of Each Defendant's Age
20   0.000511
24   0.024719
28   0.060007
32   0.045857
36   0.036481
  
63   0.003750
67   0.002898
71   0.001023
75   0.000170
79   0.000170
Name: age, Length: 64, dtype: float64
Final Disposition Description Table: 0=jail, 1=probation
Count of Each Defendant's Final Disposition Description
0    3618
1    2248
Name: fnl_disp_desc, dtype: int64
Percentage of Each Defendant's Final Disposition Description
0   0.616775
1   0.383225
Name: fnl_disp_desc, dtype: float64
*****Centering My Numerical Explanatory Variable!*****
Mean of numerical variable should be close to 0:
-8.01995133560795e-15
*****Logistic Regression Analysis!*****
All of the variables
Optimization terminated successfully.
         Current function value: 0.630450
         Iterations 8
                           Logit Regression Results                           
==============================================================================
Dep. Variable:          fnl_disp_desc   No. Observations:                 5866
Model:                          Logit   Df Residuals:                     5855
Method:                           MLE   Df Model:                           10
Date:                Tue, 23 Feb 2021   Pseudo R-squ.:                 0.05284
Time:                        21:48:09   Log-Likelihood:                -3698.2
converged:                       True   LL-Null:                       -3904.5
Covariance Type:            nonrobust   LLR p-value:                 1.927e-82
=======================================================================================
                          coef    std err          z      P>|z|      [0.025      0.975]
---------------------------------------------------------------------------------------
Intercept              -0.9637      0.092    -10.495      0.000      -1.144      -0.784
race[T.1]              -0.3461      0.099     -3.496      0.000      -0.540      -0.152
sex[T.1]                0.2716      0.061      4.435      0.000       0.152       0.392
cs_disp_less30[T.1]    -3.1583      0.454     -6.950      0.000      -4.049      -2.268
judge[T.1]             -0.0323      0.097     -0.333      0.739      -0.222       0.158
judge[T.2]             -0.0385      0.099     -0.389      0.697      -0.232       0.155
judge[T.3]             -0.0240      0.099     -0.243      0.808      -0.218       0.170
judge[T.4]             -0.0466      0.098     -0.478      0.633      -0.238       0.145
judge[T.5]             -0.0222      0.098     -0.225      0.822      -0.215       0.171
age_c                  -0.0063      0.003     -2.335      0.020      -0.012      -0.001
atty_typ_desc           0.7151      0.069     10.344      0.000       0.580       0.851
=======================================================================================
 
--------------------------------------------------------------------------------------------------
 
**********Post hoc test on just attorney type and age of defendant**********
Optimization terminated successfully.
         Current function value: 0.589638
         Iterations 5
                           Logit Regression Results                           
==============================================================================
Dep. Variable:          atty_typ_desc   No. Observations:                 5866
Model:                          Logit   Df Residuals:                     5864
Method:                           MLE   Df Model:                            1
Date:                Tue, 23 Feb 2021   Pseudo R-squ.:                0.003015
Time:                        21:48:09   Log-Likelihood:                -3458.8
converged:                       True   LL-Null:                       -3469.3
Covariance Type:            nonrobust   LLR p-value:                 4.797e-06
==============================================================================
                 coef    std err          z      P>|z|      [0.025      0.975]
------------------------------------------------------------------------------
Intercept      0.9567      0.029     32.716      0.000       0.899       1.014
age_c          0.0132      0.003      4.502      0.000       0.007       0.019
==============================================================================
Odds Ratio
Intercept   2.603170
age_c       1.013328
dtype: float64
Confidence Intervals of Odds Ratio
           Lower CI  Upper CI       OR
Intercept  2.458163  2.756731 2.603170
age_c      1.007504  1.019187 1.013328
