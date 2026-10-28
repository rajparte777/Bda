# Bda
a
Aim : To import, analyse and visualize monthly Sales and Profit data using R in RStudio. 

Introduction : 
Data visualization converts numerical or categorical data into graphical form so that patterns, 
comparisons, trends, distributions and relationships are easier to understand. R provides built-in 
functions for data analysis and visualization. RStudio is an integrated development environment 
that helps users write scripts, execute commands, inspect data and view plots in one interface. 


Software Requirements : 
• Operating system: Windows 10 or Windows 11. 
• Software: R installed on the system and RStudio Desktop. 
• R package: none required; built-in base R functions are used. 
• Input file: CSV file containing Month, Sales and Profit columns. 

Part A - Input Dataset and Algorithm 
Input Dataset 
The dataset contains the monthly Sales and Profit values for ten months, from January to October. 



Complete R Program 

# Import CSV dataset 
sales_data <- read.csv(file.choose()) 
# Display and inspect data 
print(sales_data) 
str(sales_data) 
summary(sales_data) 
colSums(is.na(sales_data)) 
# Monthly Sales bar chart 
barplot(sales_data$Sales, names.arg = sales_data$Month, 
col = "skyblue", main = "Monthly Sales", 
xlab = "Month", ylab = "Sales", border = "black") 
# Monthly Sales line chart 
plot(sales_data$Sales, type = "o", col = "blue", pch = 16, 
xaxt = "n", main = "Monthly Sales Trend", 
xlab = "Month", ylab = "Sales") 
axis(1, at = 1:nrow(sales_data), labels = sales_data$Month) 
# Sales and Profit scatter plot 
plot(sales_data$Sales, sales_data$Profit, 
main = "Sales vs Profit", xlab = "Sales", ylab = "Profit", 
col = "red", pch = 19, cex = 1.5) 
abline(lm(Profit ~ Sales, data = sales_data), col = "blue", lwd = 2) 
cor(sales_data$Sales, sales_data$Profit) 
# Histogram and box plot 
hist(sales_data$Sales, main = "Distribution of Sales", 
xlab = "Sales", ylab = "Frequency", 
col = "lightgreen", border = "black", breaks = 5) 
boxplot(sales_data$Sales, main = "Box Plot of Sales", ylab = "Sales", col = "orange", border = 
"black") 
# Comparative bar chart 
comparison_data <- rbind(sales_data$Sales, sales_data$Profit) 
barplot(comparison_data, beside = TRUE, names.arg = sales_data$Month, 
col = c("skyblue", "orange"), 
main = "Monthly Sales and Profit", xlab = "Month", ylab = "Amount") 
legend("topleft", legend = c("Sales", "Profit"), 
fill = c("skyblue", "orange"))



Observations 
Plot                                    Observation 
Bar chart                Highest Sales in September (280); lowest in January (120) 
Line chart              Sales generally increase; decreases in April, July and October 
Scatter plot           Correlation coefficient 0.998692; very strong positive relationship 
Histogram               Most Sales values lie in the 200 to 250 range 
Box plot                  Median Sales approximately 215; no outlier detected 
Comparative bar chart            Profit generally rises as Sales rise; September is highest for 
both 


Result 
The CSV dataset was successfully imported and analysed in R. Bar, line, scatter, histogram, box 
and comparative bar charts were created and interpreted. The analysis showed an overall increase 
in monthly Sales and a very strong positive relationship between Sales and Profit, with a 
correlation coefficient of 0.998692. Thus, the aim of the practical was achieved.