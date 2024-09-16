java c
ECMT 6002/6702: Econometric Applications 
1 Practice problems 
1. Consider the following linear regression model:
yt = β1 + β2x2t + β3x3t + ut, t = 1, . . . , 100.
Suppose that we want to test if
H0 = β2 = β3 = 0.                                         (1.1)
(i) Write (a) the unrestricted and restricted model for the F-test of the above hypotheses and (b) how to estimate each model.
(ii) Suppose that URSS and RRSS are given 805 and 1015, respectively. Write the F-statistic and report the test result when 5% significance level is employed.
(Note) 95% quantiles of F(a, b)

(iii) (Optional) Note that in the above F-table, the changes in the 95% quantile depending on the “df in the denominator” are very small. Can you explain why this is reasonable based on the χ2 approximation of the F distribution discussed in class?
2. Suppose that we are interested in the following hypothesis in the previous question.
H0 = β2 + β3 = 0.                                            (1.2)
(i) Write (a) the unrestricted and restricted model for the F-test of the above hypothesis and (b) how to estimate each model.
(ii) Suppose that URSS and RRSS are given 805 and 1015, respectively. Write the F-statistic and report the test result when 5% significance level is employed.
2 Empirical application 
We will consider the dataset “ECONMATH” given in Wooldridge’s textbook “Introductory Econo-metrics”. The dataset contains grade point averages and standardized test scores, along with per-formance in an introductory economics course, for students at a large public university. We con-sider the following regression model:

where
test scores : scores of a certain test, which we want to predict
GPA : GPA measured at the beginning of the semester
ACT-M : students ACT scores in math
ACT-E : students ACT scores in English
Calculus : variable taking 1 (if the student took calculus) or 0 (oth代 写ECMT 6002/6702: Econometric Applications 3SQL
代做程序编程语言erwise).
For more detailed explanation, check Wooldridge’s textbook.
Instructions:
1. The dataset contains missing values. This quite common in empirical analysis. First check these missing values (coded as "NA") and exclude individuals associated with such missing observations from the dataset if necessary. In R, this can be done by na.omit(dataset), where dataset is the matrix where each variable takes each column.
2. Compute the OLS estimates of β1, β2, β3 and β4. In R, lm(y ∼ X) can be used if y is the vector of yt and X is the (T × 5) data (independent variables) matrix. I would recommend you compute those directly.
3. Implement t-tests to examine
βj = 0                                       (2.1)
for each j. Report the test results. In R, the test results are contained in the results given by summary(lm(y ∼ X)). The results must be close to

You can also try direct computation as in Week 2 tutorial.
4. Implement F-test to examine
H0 : β2 = β3 = β4 = β5 = 0.                                   (2.3)
The test result is also reported in summary(lm(y ∼ X)). However I recommend you to do by yourself. To do this, you need to compute URSS and RRSS of the unrestricted and restricted models. In R, URSS can be computed as usq=((lm(y∼X))$residuals)2; URSS=sum(usq). RRSS can be computed as usq2=(y-mean(y))2; RRSS=sum(usq2). Then the F-test statistic can be computed as discussed in th lecture. The statistic must be close to
F = 141.2.                                            (2.4)
5. Report the test result. You may need to obtain the quantiles of the F(a, b) distribution. In R, this can be done by using “qf(0.05,a,b)” if you want 5% quantile.
6. I would recomment to do implement F-test to examine
H0 : β3 = β4 = 0.                                        (2.5)
by yourselves.
7. This computing exercise is not mandatory.





         
加QQ：99515681  WX：codinghelp
