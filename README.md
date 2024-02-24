# Chi-Square-Test

Association indicates a broad relationship where one variable gives insight into another, while correlation is a more specific term that refers to variables moving together in a particular direction. For instance, with an increasing trend, if X is greater than its mean value (μX), then Y is more likely to be greater than its mean value (μY). However, it's important to recognize that not every association is a correlation, and since causality is tied to association rather than correlation, we cannot assume causation from correlation alone (Altman & Krzywinski, 2015). Understanding associations and correlations is crucial in data analysis as they illuminate the interconnectedness of variables, guiding decision-making, risk management, and predictive modeling. Correlations suggest potential cause-and-effect relationships that merit deeper investigation, though they do not confirm causality. They are instrumental in hypothesis testing and resource allocation, helping to optimize efforts and expenditures. Properly interpreted, these statistical tools can unveil complex patterns within data, but they must be approached with critical thinking to avoid misinterpretation

Terminal Output
> correlation <- cor(data$`Years At Company`, data$`Years In Current Role`)
> 
> contingency_table <- table(data$`Business Travel`, data$`Job Role`)
> print(contingency_table)
                   
                    Healthcare Representative Human Resources Laboratory Technician Manager
  Non-Travel                               15               4                    28      12
  Travel_Frequently                        26              10                    51      13
  Travel_Rarely                            90              38                   180      77
                   
                    Manufacturing Director Research Director Research Scientist
  Non-Travel                            13                 6                 28
  Travel_Frequently                     29                12                 54
  Travel_Rarely                        103                62                210
                   
                    Sales Executive Sales Representative
  Non-Travel                     39                    5
  Travel_Frequently              59                   23
  Travel_Rarely                 228                   55
> write_csv(as.data.frame(contingency_table), "contingency_table_HR.csv")
>                                                                                         
> chi_square_test <- chisq.test(contingency_table)
> print(chi_square_test)

	Pearson's Chi-squared test

data:  contingency_table
X-squared = 11.988, df = 16, p-value = 0.7448

> 
> print(correlation)
[1] 0.7587537
> 
> ggplot(data, aes(x = `Years At Company`, y = `Years In Current Role`)) +
+   geom_point() +
+   theme_minimal() +
+   labs(title = "Scatter Plot of Years Spent at Company vs Years in Current Role",
+        x = "Years At Company",
+        y = "Years In Current Role")
