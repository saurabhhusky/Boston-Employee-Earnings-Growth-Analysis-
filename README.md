# Boston-Employee-Earnings-Growth-Analysis-


The link to this dataset is as follows, 
https://data.boston.gov/dataset/employee-earnings-report

This is a payroll Boston dataset. Each year Boston publishes this kind of dataset, so I decided to pursue this dataset. 
I was using the last 4 years of data which are 2019,2020,2021,2022.


Initial Interest:
I find analyzing employee earnings data fascinating as it allows me to uncover insights about Departments, populations, year-wise departments increment and decrements, top departments' salaries, etc. We have 90926 rows &15 columns.

•	We have the Following Variables:
'name': The name of the employee.
•	'department': The department to which the employee belongs.
•	'title': The job title or position of the employee.
•	'regular': The amount of regular pay received by the employee.
•	'retro': The amount of retroactive pay received by the employee.
•	'other': Miscellaneous pay or additional pay received by the employee.
•	'overtime': The amount of overtime pay received by the employee.
•	'injured': Pay received during a period of injury or sick leave.
•	'detail': Detailed pay breakdown or specific payment details.
•	'quinn': Quinn Bill-related pay, if applicable.
•	'total': The total pay received by the employee, including all components.
•	'zip': Potentially related to the employee's postal or ZIP code

1st I import all the necessary libraries & create the File on my desktop and put all my 4 files. As the following code shows I put my path (the files I stored). The code “*earnings, shows if u find any word which has earnings take that file and use it.
 
 <img width="468" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/b1c755fe-a30b-4547-b2f3-4767db8ad824">

There are a lot of data-cleaning processes we need to do which I’ll do in the following steps.

1.	Zip codes have very inconsistent values, so I transform them into 5 no. zip code, also there are a lot of NULL values in the zip code, so I filled in the NULL zip values using the most recent non-missing value encountered from the top.
   <img width="468" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/f3211a7f-3aa7-40df-bc47-36de3e148da0">

3.	We create a new variable “Year” from all files as each file has a year name, so we extract that and use it as a year.
4.	Co-relation analysis Findings:
•	The 'regular' and 'total' columns have the highest mean values, indicating they might be the major contributors to the overall earnings.
•	The 'retro', 'other', 'overtime', 'injured', 'detail', 'Quinn', and 'zip' columns have lower mean values, indicating they may contribute less to the overall earnings.
•	The 'regular' column has a considerable standard deviation, suggesting a wide variability in regular pay among employees.
•	The 'retro', 'other', 'overtime', 'injured', 'detail', 'Quinn', 'total', and 'zip' columns also show notable standard deviations, indicating variability in these components as well.

Were there any outliers or suspicious data?

based on the basic analysis I performed, I might want to investigate further exploratory data analysis to identify outliers or unusual patterns in the data. I can use box plots, histograms, or scatter plots to visualize the distribution of numerical variables and detect any potential outliers.
    
The boxplot shows the distribution of data for each variable. The box represents the interquartile range (IQR), and the whiskers extend to show the range of "normal" data points. Points beyond the whiskers are considered outliers.

Regular: The data points are concentrated between 0.2 to 0.4, within the whiskers, indicating that most of the data falls within this range, with some variation.

Other: There are outliers beyond the range of 1.0 to 1.2. These data points are unusual or different from the rest of the data in terms of their values.

Total: The whisker extends up to the value of 1.0, also some have residual in 0.8 to 0. This suggests that the data is widely spread, and there are extreme outliers.

Injured: The data show there are some outliers present in 0.6 & 0.8 but it’s not a lot.

 
 <img width="282" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/4c556a15-1cda-49a7-bd09-d7c89ff7e6da">


Explaining co-relation matrix !

Regular earnings have a strong positive correlation with total earnings (0.86), indicating that they significantly contribute to an employee's overall earnings. Regular earnings also show moderate positive correlations with overtime (0.34) and detail (0.17).

Retro earnings have a weak positive correlation with total earnings (0.19).
Retro earnings have very low correlations with other earning components, suggesting a limited relationship with them.

Other earnings show relatively low correlations with other components, indicating weak relationships.

Overtime earnings have moderate positive correlations with total earnings (0.62) and detail (0.38).

Injured earnings have a weak positive correlation with total earnings (0.16) and other components.

Detail earnings show moderate positive correlations with overtime (0.38) and total earnings (0.4).

Quinn earnings have a moderate positive correlation with overtime (0.47) and total earnings (0.45).
In conclusion, the correlation matrix provides insights into the relationships between various earning components. It highlights the strong correlation of regular earnings with total earnings, as well as some moderate correlations between certain earnings components. Correlation analysis is valuable in understanding how different components interact and influence an employee's overall earnings, which can assist in making informed decisions and conducting further data analysis.





Business questions

1.	What are the top 20 department titles & count?
 <img width="324" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/89bd5a31-dd8f-4658-bf6e-ae64dea5689c">


2. What is the count of unique job titles & the count of unique jobs in the last 4 years? 
<img width="324" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/1e7e09b1-7433-450b-aa42-d529bacc20ef">

The analysis of unique job titles and job counts in the last 4 years provides valuable insights into the dataset. By comparing these counts, we can gain a glimpse of the data and identify jobs that were present in previous years but not in 2022. This comparison helps us identify departments that might have closed or undergone name changes.

It is evident that the number of job titles decreased in 2022, with only 1700 unique job titles compared to the highest count in 2021. This decline could be attributed to the impact of external factors like the COVID pandemic in 2021 and a subsequent recession in 2022. Moreover, there is a possibility of data cleaning or consolidation in 2022, leading to a rise in unique departments with new positions such as HR analysts.

Overall, the analysis of unique job titles and job counts offers valuable information about the changes and dynamics within the dataset, enabling us to make informed decisions and understand the evolving job landscape over the years.
 

Cleaning the Department and Title

In our dataset, we have a lot of titles, departments that fall under the same departments. We have many short forms that I want to clean. I am focusing on the Top 5 salary departments. I will map the specific titles to their respective departments. Additionally, I created a variable to save all the changes I am making.

The top 1st salaried department is 'Boston Public Schools', also known as 'BPS'. As we can see, many departments come under BPS, so we will rename them to 'Boston Public Schools' to maintain consistency.
 
<img width="468" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/a2ee24e6-6f0e-455f-9754-a7cc8dc3105c">


My primary objective is to identify the unique departments for the years 2021 and 2022. As the dataset is extensive, I will focus on the data for the last two years. I want to compare the unique departments from the last two years and determine if any departments were present in both years or not. This analysis will help me understand the changes or consistency in department composition over time. 
<img width="468" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/72055c5f-f073-4c85-8914-60efd6ea9423">

The code reveals the school departments that existed in the year 2021 but are not present in the year 2022. Specifically, three departments were identified as absent in 2022: the Office of RRE, Neighborhood Development, and Office of Economic Development.

So, as I know, our data is inconsistent, I am going to work on the upper three departments. Using the internet, I am going to find out what's the alternative names of these departments. As the following code shows, we found the departments which are referred to as BPS Business Services, Office of Housing & Road to Success.

The purpose of this step is to ensure consistency in department names across both years. By mapping certain department names to their updated names, the data is standardized for further analysis and comparison.

 <img width="468" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/07c84091-262a-4bd6-bba2-fc63dcf1d7b3">



We are going to clean the departments and do the same with the Boston police, Fire departments.

Combining/consolidating the titles & departments:
 Boston Police Department:
The analysis of the 'Boston Police Department dataset reveals the most common police department titles before and after consolidation. Additionally, it provides a comparison of the unique title counts for the top 10 years in the dataset.

The plots offer valuable insights into the impact of consolidation on title frequencies and the distribution of titles across different years. After data cleaning and consolidation, we observe a reduction in the counts of police officers, detectives, and police sergeants, indicating a streamlining of these positions.

On the other hand, titles such as call taker and clerk show minimal changes in count, as they have relatively small numbers. However, when we focus on higher positions like police officers and detectives, we gain a clearer vision of the data after cleaning. Notably, in 2022, there is an increment in the number of unique titles, and the cleaned data provides a much clearer and more detailed view of the job landscape.

Overall, this analysis helps us understand the effects of consolidation on job titles and provides a more refined perspective on the dataset, enabling us to make informed decisions and gain better insights into the distribution and trends of job titles over time.
 <img width="390" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/e15c94b3-5421-44bd-8e35-ff1b27be468f">

Fire department:
The fire department holds a crucial role in every city, and I deeply respect their contributions. After performing data cleaning, we observe significant differences in the departments. The key titles within the fire department are fire fighter and fire lieutenant, and their counts remain consistent across the years after cleaning. This indicates that the Boston Fire Department maintains a stable and steady structure in terms of titles, showcasing a sense of continuity and consistency in its workforce. 
<img width="468" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/f7edfb00-96f9-471b-b79a-289874439b7c">

Old vs Cleaned Titles & Departments visualizations
After conducting thorough data cleaning, we can clearly observe its significance through the following visualizations. By comparing the original titles and departments with the newly cleaned and grouped ones, we gain valuable insights.
<img width="468" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/e0750ba3-770d-492f-9b6a-8a72bff309bf">

The graph vividly illustrates that the number of job titles increased by approximately 1300 to 1500 in 2022. This suggests that even during times of recession, there are new job opportunities emerging. Additionally, the previous title counts show that we had over 1600 job titles in the market in 2022. If we had used this data without cleaning, we would have encountered more outliers, resulting in an inconsistent model.

Turning our attention to the departments, the visualization highlights the substantial impact of the cleaning process. Although we don't observe a significant increase in the number of departments, there is a notable difference when comparing 2022 to 2019, where we have 57 new unique departments. This indicates that some new departments were created or identified during the cleaning process, providing a more accurate and comprehensive representation of the data.
 

Feature Engineering

We created 2 new variables ‘average total earnings per capita’ & ‘average regular earnings per capita’.

Average total earnings per capita: variable provides an average measure of total earnings per person, which can be useful for understanding the overall earnings distribution and trends within the dataset.

Average regular earnings per capita: provides an average measure of regular earnings (excluding any additional earnings like overtime or bonuses) per person, which can offer insights into the compensation structure within the dataset.

Population Trend: The population of Boston has been decreasing from around 700,000 in 2019 to approximately 660,000 in 2022. This downward trend indicates that the city's population is experiencing a decline over the years.

Average Wage Index (AWI) Trend: The AWI in Boston has been increasing consistently over the years. In 2021, it was around 61,000, and in 2022, it rose to approximately 67,000. This upward trend suggests that the average wage level in the city has been growing.
The declining population might indicate various factors, such as migration patterns, changes in demographics, or economic conditions. It could mean that people are moving out of the city, 
The rising Average Wage Index signifies an improvement in wage levels for the employed population. This could be due to factors like economic growth, increased job opportunities, or wage growth in various sectors.
 <img width="309" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/c6947c1c-2ad4-425d-9664-3b215c82750e">
 <img width="375" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/61c38a9a-8540-4231-aca4-3e4faa010645">
 <img width="468" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/98445c4c-9bca-4efa-bb71-5a5537f1acd7">



 

 

The total regular earnings for all individuals in the dataset in 2021 were around $1.55 billion, while the total earnings (including regular and other components) were approximately $1.87 billion. The data was collected for 22,546 individuals, and the average total earnings per capita were about $82,792.66. On average, everyone earned approximately $68,905.35 from regular earnings.

The total regular earnings for all individuals in the dataset in 2022 were around $1.60 billion, while the total earnings (including regular and other components) were approximately $1.93 billion. The data was collected for 23,204 individuals, and the average total earnings per capita were about $83,202.26. On average, everyone earned approximately $68,985.55 from regular earnings.

I want to find an average wedge index (awi)using the Boston population. I used awi and population of the last 4 years from the internet which are the years 2019 to 2022.
Here's what each part of the output represents:

Bar Chart: The blue bars represent the average earnings per employee for each year. This bar chart shows the trend in average earnings across the years 2017 to 2022.

Red Line: The red line represents the trend of regular earnings over the years. It provides a visual representation of how regular earnings have changed from 2017 to 2022.

Yellow Line: The yellow line represents the trend of the SSA average wage index over the years. The SSA average wage index is a measure of wage inflation, and this line shows how it has evolved from 2017 to 2022.


        <img width="205" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/93b6b7d5-30a0-4d80-9e72-87469664ec6c">
        The visualization shows that regular earnings have experienced fluctuations over the years, with a notable increase in 2021 followed by a slight decline in 2022. In contrast, the SSA average wage index has remained relatively stable during the same period.![image](https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/ba929540-e6da-431b-a272-7f9423d2f125)






The correlation analysis examines all numeric variables, excluding Quinn data and using the clean dataset (which contains the new variable). We observe that the police and fire departments exhibit a direct correlation with the variables detail, retro, other, and injured.

Furthermore, the variables detail and overtime show similar patterns in their correlations.

 
<img width="503" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/8cca06da-e1ca-4e3e-a181-50b8b622632e">



The Following plot shows how the total earnings have changed over time, allowing us to observe any overall trends or patterns in the data.

<img width="468" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/a052b697-0e70-4cc2-8809-87f986889d6a">


 

Regression analysis
We are going to create a model which shows which employees are likely to accept to do overtime using regular and overtime variables.

The code filters the 'earnings' dataset to only include records from the year 2022 and where the 'overtime' earnings are greater than 1.   Each data point in the plot represents an employee's earnings for the year 2022. The regression line on the plot helps visualize the correlation or relationship between 'regular' and 'overtime' earnings.

In summary, the plot allows us to examine the relation between regular and overtime earnings for employees in 2022, enabling us to identify any potential patterns or trends in the data that relate to these two variables. There are 6805 employees there.
 
<img width="199" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/c88bd3a0-0463-4943-b8ca-6d6b8e9e449d">



So now we are creating a condition for people who like to do overtime. The following code shows the dataset select records where the sum of 'overtime' and 'regular' earnings is greater than 50,000, but less than 130,000. It also filters for records where 'overtime' earnings are greater than 6,000 and the ratio of 'overtime' to 'regular' earnings is between 0.25 and 1.5. 

So, 25 % means, we’re going 2 compare regular income and overtime income if it’s lower than 25% it means they don’t like to do overtime or they don’t want to go for overtime & if it’s lower than 15 % means they like to do overtime (Human psychology often suggests that when individuals earn a sufficient income, they may be less inclined to work overtime, unless they hold higher positions)

 <img width="468" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/840ff022-dedf-4cce-bbf6-0f12f682dd26">


In this, we chose the lower salary income employees. Overall, the regression analysis shows that for employees falling within the specified 'normal' income levels and meeting the defined conditions, there is a positive correlation between 'regular' and 'overtime' earnings. 
As 'regular' earnings increase, 'overtime' earnings tend to increase as well, which is reflected in the upward trend of the regression line. There are some outliers present.
<img width="216" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/b3aa0010-c769-4a9a-9353-a80a07c198e9">

 

The R-squared value of 54.6% indicates that the 'quinn' variable has a substantial influence on predicting 'regular' earnings, explaining more than half of the variability in 'regular' earnings. This result suggests that 'quinn' plays a significant role in determining an employee's 'regular' earnings.

Salary distribution of top departments
The graph illustrates the salary distribution among different departments. The Fire Department stands out as the highest-paid department, with salaries ranging between 70k to the highest at 130k. The Boston Police Department maintains a consistent salary range between 90k and 100k. On the other hand, Boston Public Schools have the lowest salaries, starting at 40k. Notably, no department has salaries below 50k.
 
<img width="328" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/522430e9-3d70-4daa-b14c-2f9508858798">


Now we’ll want to see the employee who received Quinn's income and what kind of degree they pursued.

 In this code, I calculate the income increase percentage for each employee by comparing their regular and quinn incomes. We then categorize employees into 'Master,' 'Bachelor,' 'Associate,' or 'No Higher Degree' based on their income increase percentage (I got the information on the internet, If the income increase percentage is greater than or equal to 25%, the employee is classified as having a 'Master' degree. If it is between 20% and 25%, they are classified as having a 'Bachelor' degree. If it is between 10% and 20%, they are classified as having an 'Associate' degree. Any income increase percentage less than 10% results in the employee being classified as having 'No Higher Degree'.

The code shows the count of employees in each category for every year and plots a bar chart to visualize the number of employees with different degree qualifications over time. The Quinn bill might impact both quinn and regular incomes, influencing the degree qualifications of employees.

The stacked bar chart clearly illustrates the importance of pursuing a master’s degree. Employees with a master’s degree experience a noticeable increase in their pay salary compared to those without any higher degree. In 2022, around 10% of employees did not pursue any degree, while approximately 5% of employees in each year opted for a master’s degree. On the contrary, the number of employees without any higher degree has declined over the years. This trend indicates that having a master’s degree can significantly impact an employee's earning potential and may be a valuable investment in one's career growth.
 <img width="468" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/162afe05-eb69-4816-82ac-a2a62a909007">


In the next steps of my data analysis, I am focusing on zip codes to understand the distribution of high and low-income individuals. To accomplish this, I have installed the required libraries and downloaded Boston-specific zip code files and the national zip codes file, which contain latitude and longitude data.

In my code, I first read the zip code, latitude, and longitude data, as well as the earnings data for the year 2022. I then process this data to calculate the number of employees per zip code and merge it with Boston-specific zip code information. The 'boston' and 'suburbs', contain relevant data that can be used to create various maps visualizing the distribution of employees in Boston and its suburbs based on zip codes.

Next, I will further segregate the employees based on their income levels into 'rich' and 'poor'. In the 'rich' category, employees have overall earnings of $150,000 or more, while in the 'poor' category, employees have 'total' earnings less than $60,000 and greater than or equal to $20,000.

The initial visualization of this data shows that a significant number of employees reside near the Dorchester area (zip code 1750), while a smaller number of people live near the Boston area.

There another analysis is the employer who’s earning good residing in the Dorchester area as Dorchester area are even don’t come under a safe area. It will give a good insight if we dig more into this co-relation.
  
 
<img width="361" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/c3aad074-232e-4fdf-ac2b-b7aebd025dda">
<img width="468" alt="image" src="https://github.com/BASH-EPIC/Boston-Employee-Earnings-Growth-Analysis-/assets/81670865/5fa7dfe9-0b99-41c2-b001-b0472b4c623b">




Interpretation of Results:

1.	Correlation Analysis:
The correlation analysis indicates that regular earnings have a strong positive correlation with total earnings, implying that regular pay is a significant driver of an employee's overall earnings. On the other hand, other earnings components, such as retro, overtime, injured, and detail, show weaker correlations, suggesting their relatively lesser impact on total earnings.

2.	Regression Analysis:
The regression analysis demonstrates that the 'quinn' variable is a crucial predictor of 'regular' earnings, explaining more than half (54.6%) of the variability in regular earnings. This highlights the importance of considering the 'quinn' component in understanding and estimating an employee's regular pay.

3.	Degree Qualification Analysis:
The analysis of income increase percentage and degree qualifications reveals that a substantial number of employees pursued master's degrees, followed by bachelor's and associate degrees. This suggests a possible correlation between education level and income increase, which could be an essential aspect to consider when assessing employees' career growth.

Recommendations:

1.	Salary Structure Evaluation:
Given the strong correlation between regular earnings and total earnings, stakeholders or policymakers should thoroughly assess the existing salary structure. Understanding the contribution of each earnings component to the overall pay can aid in developing equitable and competitive compensation plans for employees.

2.	'Quinn' Component Impact Assessment:
Considering the significant role of the 'quinn' variable in predicting regular earnings, policymakers should conduct a comprehensive evaluation of the impact of the Quinn Bill on employee compensation. This analysis can provide insights into whether the Quinn Bill achieves its intended objectives and whether any adjustments are necessary.


3.	Performance-Based Incentives:
To encourage higher performance and productivity, policymakers could explore incorporating performance-based pay structures. Linking pay increases to employees' performance evaluations can create a performance-driven culture and reward exceptional contributions.

4.	Employee Engagement Strategies:
Analyzing factors influencing employees' decisions to accept or decline overtime can help policymakers design effective employee engagement and retention strategies. Offering incentives, flexible work arrangements, and a positive work environment can motivate employees to participate in overtime opportunities.

References:

•	Turanga. (n.d.). Boston-Earnings-Analysis/0_Boston_Data_Wrangling.ipynb at master · Turanga1/Boston-Earnings-Analysis. GitHub. https://github.com/Turanga1/Boston-Earnings-Analysis/blob/master/0_Boston_Data_Wrangling.ipynb

•	Wheeler, A. (2021, March 15). Boston Department’s Average Earnings for Employees in Comparison to all Employee Earnings. Observable. https://observablehq.com/@aliciawheeler19/boston-departments-average-earnings-for-employees-in-comp

•	Turanga. (n.d.). Boston-Earnings-Analysis/earnings.csv at master · Turanga1/Boston-Earnings-Analysis. GitHub. https://github.com/Turanga1/Boston-Earnings-Analysis/blob/master/earnings.csv
•	Commonwealth of Massachusetts. (n.d.). Department of Developmental Services. Mass.gov. https://www.mass.gov/orgs/department-of-developmental-services
•	Average Wage Index (AWI). (n.d.). https://www.ssa.gov/oact/cola/awidevelop.html
•	Marytj. (2017). Chicago Payroll data visualization. Kaggle. https://www.kaggle.com/code/marytj/chicago-payroll-data-visualization
