# Power-BI-Visualization

## ETL Process Using DAX and M Language
In this project, I analyzed sales records for a manufacturer that produces bikes, clothes, accessories, and components, with data spanning from 2018 to 2020. Due to the manageable size of the dataset, I utilized Excel worksheets for the raw data.

![Screenshot 2024-07-25 184549](https://github.com/user-attachments/assets/52b7336a-321f-4a3f-a6de-4b5672795000)

### Difference Between DAX and M Language:
DAX (Data Analysis Expressions) and M (Power Query M Formula Language) are both used in Power BI but for different purposes:
- DAX is used for calculations and data modeling within Power BI.
- M is used for data transformation and preparation in Power Query before data is imported into Power BI.
Most data cleaning and type transformations were performed using M language in Power Query. Once the data was imported into Power BI, additional transformations were carried out using DAX.

### ETL Process Details
Before exporting the data to Power BI, I defined primary keys for each table to establish relationships for data modeling. To relate dates effectively, I created a calendar table using Power BI’s New Table feature with the following DAX code:

`CALENDAR(DATE(2017,7,1), MAX(Orders[OrderDate])+60)`

This code generates a column with date values, from which I derived Month and Year columns. To calculate the fiscal year, I used this DAX formula:

`Fiscal Year = IF(Calender[Month Num]>6, Calender[Year]+1, Calender[Year])`

To format dates as 'MMM-YYYY', I created a YearMonth column with:

‍‍‍‍‍‍‍‍`YearMonth = FORMAT(DATE(Calender[Year],Calender[Month Num],1),"MMM-YYYY")`

### Data modelling 
Primary keys are used to relate tables to each other, similar to  join queries in SQL:

![Screenshot 2024-07-25 221138](https://github.com/user-attachments/assets/a40fcb5c-1b1b-4fe6-a6ed-f696d1e50020)


## Visualization 

![Screenshot 2024-07-25 174108](https://github.com/user-attachments/assets/7ebdffb9-e64d-452a-a2d2-4c34600f9f08)






