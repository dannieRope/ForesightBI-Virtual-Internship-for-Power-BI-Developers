I participated in the ForsightBi internship tailored for PowerBi developers, and this experience significantly strengthened my proficiency in generating reports within Power BI.

The program is structured to offer you the chance to apply Power BI to resolve actual Reporting and Analytics challenges. During this internship, I successfully created my inaugural report in Power BI Desktop.

#  BACKGROUND 

![FORGITH](https://github.com/dannieRope/ForesightBI-Virtual-Internship-for-Power-BI-Developers/assets/132214828/83fb3902-6720-46da-8f76-bfda895523d5)


Forggith Pharmaceuticals (Forggith) is a Pharmaceutical Manufacturing company based in Germany. As a Manufacturing company, they produce medical drugs that get to consumers through their Distributors.

Forggith provided a template for their distributors to capture records of their sales, which are then sent to Forggith on a monthly basis. This data is then used for reporting and analysis by Forggith to achieve their sales and Marketing objectives through tracking and monitoring of KPIs.

In their efforts to maximize growth, Forggith works with a team of Sales and Marketing pros who ensure retailers are able to get their products through distributors. That is, Forggith does not sell directly to retailers or end-users, they sell to Distributors. But they maintain interaction with retailers, through their Sales and Marketing pros.

#  POWER BI REPORTING REQUIREMENTS

Forggith is looking to create some Power BI Reports to assist in guiding their strategies, tactics, and operations as a company. For a start, they have identified a couple of numbers they will like to report from their data.

## Sales Performance Overview (Sliced by: Year, Month, Quarter, Team)

**-Total Revenue**

**-Total Revenue Year To Date (YTD)**

**-Total Revenue Previous Year YTD**

**-Total Revenue Same Period Last Year(SPLY)**

**-Total Target**

**-Total TargetYTD**

**-Actual Revenue Performance Previous Year YTD vs Target Previous Year YTD**

**-Actual Revenue Performance YTD vs Target YTD**

**-Revenue Month-on-Month Percentage Change**

**-Revenue Distribution by Location**

**-Revenue by Channel**

**-Revenue by Product Class**


##  Marketing Performance (Slice by Year, Quarter, Month, Product Category and Team)

**-Revenue Achieved vs Revenue Target***

**-Volume Achieved vs Volume Target**

**-Actual Revenue by Sales Representative**

**-Target Revenue Achievement by Sales Representative**

**-Actual Volume by Sales Representative**

**-Target Volume Achievement by Sales Representative**

**-Actual Revenue Achievement by Sales Team**

**-Revenue and Volume Achievement by Product**


## Here are ideas of how these reports will be used:

*The Sales Representative can track their performances throughout the period to plan their marketing activities.*

*The Team Managers can track their teams' performances throughout the periods to plan their teams' activities.*

*The executive team can track Revenue numbers to monitor alignment with the set targets and influence medium- to long-term strategies.*

**Note: You are to use the company's standard colors across your reports.**

# THE DATASETS

Two datasets were provided: the sales dataset and the target dataset. Below is a tables the datasets used, along with their respective columns and descriptions:

**-DimLocation Table**



*LocationID:* Unique identification number for each location (primary key)

*City:* the city where the transaction took place

*Latitude:* The latitude of the location where the transaction took place

*Longitude:* The Longitude of the location where the transaction took place



**-DimSubChannel Table**



*SubChannelID:* Unique identification number for each sub-channel (primary key)

*ChannelID:* Unique identification number for each channel (foreign Key)

*Sub-channel:* sub-channel for the distribution


**-DimChannel Table**



*ChannelID:* Unique identification number for each distribution channel (primary key)

*Channel:* The distribution channels



**-DimProducts Table**


*ProductID:* Unique identification number for each product (Primary key)

*ProductName:* The name of each product

*ProductClass:* The class to which each product belongs

*Product Price:* The selling price of each product



**-DimEmployee Table**


*ID:* Unique identification number of each employee (primary key)

*Name:* The name of the employees

*Manager:* Name of the manager of the employees

*Team:* The team to which the Manager and the employee belong



**-Sales Table**


*Sales ID:* Unique identification number for each sales transaction (primary key)

*MonthYear:* The month and year the transaction took place

*SalesRepID:* The unique identification number of the salesperson who made the transaction (foreign key)

*Distributor:* The unique identification number of the salesperson who made the transaction (foreign key)

*Customer Name:* The unique identification number of the salesperson who made the transaction (foreign key)

*LocationID:* The unique identification number of the salesperson who made the transaction (foreign key)

*SubChannelID:* The unique identification number of the salesperson who made the transaction (foreign key)

*ProductID:* The unique identification number of the salesperson who made the transaction (foreign key)

*Quantity:* The unique identification number of the salesperson who made the transaction (foreign key)



**-Target Table**


*ProductID:* unique identification number of the products

*SalesRepID:* The unique identification number of the salesperson who made the transaction (foreign key)

*Month:* Month of the year the transactions took place

*2022:* sales target for the year 2022

*2023:* sales target for the year 2023

*2024:* sales target for the year 2024

*2025:* sales target for the year 2025



## WORKING WITH THE DATASETS

**-SALES DATA**

The sales data consists of the following tables:

1 DimChannel

2 DimEmployee

3 DimProduct

4 DimLocation

5 DimSubchannel 

6 Sales2022

7 Sales2023-2025

When loading the dataset into the Power Query Editor, it seems that everything is in order except for the DimEmployees table. To correct this, I promoted the first rows of the DimEmployees table as headers.
Additionally, I appended the Sales2022 and Sales2023-2025 tables since they share the same column names, enabling me to access sales details from 2022 to 2025 seamlessly.

To use the first rows in the DimEmployees table as headers,I followed these steps:

1. In the Power Query Editor, navigate to the Transform tab.
   
2. Locate and click on the "Use First Rows as Headers" feature.
   
3. This action will promote the first rows of the DimEmployees table as headers, ensuring that the data is structured correctly.

   
   
   *Before using "Use First Rows as Headers" feature*
   
   ![before](https://github.com/dannieRope/ForesightBI-Virtual-Internship-for-Power-BI-Developers/assets/132214828/a66ff10e-f032-4aa0-8eca-90a2586e528a)

   

   *After using "Use First Rows as Headers" feature*
   
   ![after](https://github.com/dannieRope/ForesightBI-Virtual-Internship-for-Power-BI-Developers/assets/132214828/238d303d-ce52-4b7b-a0cc-84bb6aa1b1bf)



   
I combined the Sales2022 and Sales2023-2025 tables in the Power Query Editor, following these steps:

1. Click on one of the tables (e.g., Sales2022).
   
2. Go to the Home tab in the Power Query Editor.
   
3. In the Combine ribbon, click on "Append Queries."
   
4. From the drop-down menu, select "Append Queries."

This action will append the data from Sales2023-2025 to Sales2022, consolidating the information from these tables.

   *Result after combining both tables*
   
   ![result](https://github.com/dannieRope/ForesightBI-Virtual-Internship-for-Power-BI-Developers/assets/132214828/8ba29484-f121-4dfd-affa-236f12cb115f)



**-TARGET DATA**

There's just one table here, which is the "target table." 
It comprises six columns: SalesId, ProductId, Months, and individual columns for the years 2022, 2023, 2024, and 2025.
To improve its structure, I elevated the initial rows to serve as headers and consolidated the columns for 2022, 2023, 2024, and 2025 into a single "Year" column through an unpivoting process.

I performed the unpivoting process with the following steps:

1. Select the "SalesId," "ProductId," and "Months" columns.

2. In the Transform tab, click on "Unpivot Columns," and then select "Unpivot Other Columns" from the drop-down menu.

This action consolidated the individual year columns (2022, 2023, 2024, and 2025) into a single "Year" column, allowing for more convenient data analysis.


*Before Unpivoting*


![before unpivot](https://github.com/dannieRope/ForesightBI-Virtual-Internship-for-Power-BI-Developers/assets/132214828/41c75eb5-6d0d-4a64-9d5c-64afea91f853)



*After Unpivoting*


![After unpivot](https://github.com/dannieRope/ForesightBI-Virtual-Internship-for-Power-BI-Developers/assets/132214828/9281ba8a-61ac-4602-9f5c-7d9dedaf10a2)





# DATA MODELING PROCESS

I employed the Star Schema data modeling approach for this task. In Power BI modeling, the Star Schema stands out as a recommended practice, often favored over alternatives like the Snowflake Schema. 
This preference is primarily driven by its simplicity and performance benefits. 
It facilitates intuitive and effective reporting, rendering it a valuable option for business intelligence and analytics solutions.

Initially, the model comprised five dimension tables and two fact tables, which are detailed below:

**Dimension tables**:
- DimEmployees
- DimLocation
- DimProducts
- DimChannel
- DimSubchannel

**Fact tables**:
- Sales
- Target

Subsequently, I merged DimChannel and DimSubchannel into one, resulting in a reduction of the dimension tables to four. This decision was made to denormalize these two tables, completing a star schema model.

*Before modeling to star Schema*

![Data modeling Start](https://github.com/dannieRope/ForesightBI-Virtual-Internship-for-Power-BI-Developers/assets/132214828/08b86ae8-1272-4396-8521-446d3bbf94e1)



*After modeling to Star Schema*

![Data modelling final](https://github.com/dannieRope/ForesightBI-Virtual-Internship-for-Power-BI-Developers/assets/132214828/e48c901a-31a3-43b6-a9a0-0d7d76161bee)





I also created a calendar table 
A calendar table provides an easy way to filter and slice your data by date. It allows users to select specific time periods, such as days, weeks, months, or years, and interactively explore data within those time frames
I generated the calendar table using this formula

Calendar =   
            
            ADDCOLUMNS(
            CALENDARAUTO(),
            "Year",FORMAT([Date],"YYYY"),
            
            "Quater",FORMAT([Date],"\QQ"),
            
            "MonthName",FORMAT([Date],"MMM"),
            
            "MonthNumber",MONTH([Date])).
            
And mark the table as a date table.

*Creating the Calendar Table*

![calendar table](https://github.com/dannieRope/ForesightBI-Virtual-Internship-for-Power-BI-Developers/assets/132214828/7b0143f8-6c7a-4688-8bb6-b6218d290d9a)



*Final Model*

![Final Final Model](https://github.com/dannieRope/ForesightBI-Virtual-Internship-for-Power-BI-Developers/assets/132214828/a178cbe9-17fb-4554-bad4-55522a363baa)



## Drafting a mockup Report

I drafted a mockup report on a white board,showing the layout of what each of my reports will look like, including a representation of the types of charts to use with titles.This does not have to be drawn with straight hands, as it should be a mere representation of the report's design.

*The mockup report*

![mocku up report](https://github.com/dannieRope/ForesightBI-Virtual-Internship-for-Power-BI-Developers/assets/132214828/59a77df8-75e7-4e61-afd2-85dc76ee2b43)



Creating DAX measures for the requirement numbers
These are the DAX measures I created:


Actual_Revenue =
                 
                SUM(ActualSales[ActualRevenue])


                
Actual_Volume =
                
                SUM(ActualSales[Quantity])



Total_Target = 
               
                SUM(Targets[TargetRevenue] )


TargetVolume = 

                SUM(Targets[TargetQty])




Total_RevenueYTD =
                   
                TOTALYTD([Actual_Revenue],'Calendar'[Date])

Total_RevenueSPLY = 
                
                CALCULATE([Actual_Revenue],SAMEPERIODLASTYEAR('Calendar'[Date]))


Total_RevenuePreviousYTD = 
                
                TOTALYTD([Total_RevenuePreviousYear], SAMEPERIODLASTYEAR('Calendar'[Date]))
                
Total_TargetPreviousYTD = 
                
                TOTALYTD([Total_TargetPreviousYear],SAMEPERIODLASTYEAR('Calendar'[Date]))
                
Total_TargetPreviousYear =
                
                CALCULATE([Total_Target],PREVIOUSYEAR('Calendar'[Date]))
                
Total_TargetYTD = 
                
                TOTALYTD([Total_Target],'Calendar'[Date])
                
Target_QuantitySPLY = 
                
                CALCULATE([TargetVolume],SAMEPERIODLASTYEAR('Calendar'[Date]))

YoY%_Revenue = 
               
               VAR Previous_Yr = CALCULATE([Actual_Revenue],PREVIOUSYEAR('Calendar'[Date]))
               VAR Current_Yr = [Actual_Revenue]
               RETURN  DIVIDE((Current_Yr-Previous_Yr),Previous_Yr,0)

MoM%_Revenue = 
              
               VAR Previous_month = CALCULATE([Actual_Revenue],PREVIOUSMONTH('Calendar'[Date]))
               VAR Current_month = [Actual_Revenue]
               RETURN  DIVIDE((Current_month-Previous_month),Previous_month,0)
               

# THE REPORT: -DATA VISUALIZATION 


## THE FIRST PAGE - SALES OVERVIEW.

![Sales Overview](https://github.com/dannieRope/ForesightBI-Virtual-Internship-for-Power-BI-Developers/assets/132214828/9be50190-6e06-4dec-aa05-a60bb9b25fd7)



On the report's initial page, labeled "Sales Overview," the primary objective is to offer a comprehensive view of the sales data through key visualizations and questions addressed:

1. **Top Revenue Generator**: Represented by a lollipop chart, this visualization identifies the product that has generated the highest revenue, making it visually striking and informative.

2. **Top 10 Cities with the Highest Revenue**: Displayed by a horizontal bar chart, showcasing the top 10 cities that have contributed the most to the revenue.

3. **Revenue Distribution by Channels**: Illustrated by a donut chart, this visualization provides a clear breakdown of the percentage of revenue contributed by each channel, allowing for a quick understanding of channel performance.

4. **Month-to-Month Revenue Change**: Utilizing a waterfall chart, this visualization highlights month-on-month changes in revenue over time, enabling the audience to visualize trends, fluctuations, and seasonality.

5. **Yearly Revenue Trends**: Presented through a visual, potentially a multi-year line chart, this visualization offers insights into revenue trends over several years. It provides a broader perspective on the overall revenue performance.

These visualizations and accompanying insights on the first page of the report will deliver a comprehensive overview of sales, including product performance, city contributions, channel distribution, revenue fluctuations, and long-term trends, providing valuable insights for decision-making and analysis.

## THE SECOND PAGE - MARKET PERFORMANCE.

On the second page of the report, titled "Market Performance," the focus is on providing insights into the performance of the market. Here are the key visualizations and questions addressed:

1. **Revenue and Target Revenue by Month**: Visualized through a combination of a line chart and clustered column chart, this representation identifies the revenue generated and compares it to the target revenue on a monthly basis, enabling performance assessment.

2. **Actual Revenue and RevenueSPLY by Product Class**: Displayed using a horizontal bar chart, this visualization compares the current revenue to the revenue generated in the previous year, categorized by product class, facilitating product class performance analysis.

3. **Actual Revenue and RevenueSPLY by Year**: Illustrated via a line chart, this visualization offers a trend analysis of current revenue as well as revenue from previous years, providing insights into revenue growth or decline over time.

4. **Actual Revenue and RevenueSPLY by Top 5 Distributors**: Utilizing a horizontal bar chart, this visualization highlights a comparison between the current revenue and revenue generated in the previous year by the Top 5 distributors, aiding in distributor performance assessment.

5. **Revenue by Channel and Subchannel**: Presented through a percentage-clustered bar chart, this visualization offers an overview of revenue distribution by channel and subchannel, providing insights into channel performance and subchannel contributions.

These visualizations and insights on the second page of the report offer a detailed examination of market performance, including monthly revenue achievements, year-over-year comparisons, product class analysis, distributor contributions, and channel/subchannel performance, aiding in informed decision-making and market assessment.


## THE LAST PAGE - TEAM PERFORMANCE
On the last page of the report, titled "Team Performance," the primary focus is on evaluating the performance of the sales team. Here are the key visualizations and questions addressed:

1. **Actual Revenue and Target Revenue by Sales Representatives**: Depicted using a combined line and clustered column chart, this visualization provides a comparison of the revenue achieved by individual sales representatives against their respective targets, offering insights into sales performance.

2. **Actual Quantity Sold and Target Quantity by Sales Representatives**: Presented through a column bar chart, this visualization showcases the actual quantity sold by sales representatives in comparison to their target quantities, helping to assess sales effectiveness.

3. **Actual Revenue and RevenueSPLY by Sales Team**: Illustrated via a bar-in-bar column chart, this visualization compares the actual revenue generated by sales teams to their targets, while also providing a comparison to the revenue from the previous year, allowing for team-level performance assessment.

These visualizations and insights on the last page of the report offer a comprehensive evaluation of team performance, including revenue achievements and quantity sold comparisons. This aids in understanding how individual sales representatives and sales teams are performing in relation to their targets and historical data, facilitating informed decision-making and team management.







