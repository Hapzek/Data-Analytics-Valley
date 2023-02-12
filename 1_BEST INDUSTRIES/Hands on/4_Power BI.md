### Data Modelling

Under the hood we already worked out the data model of our dashboard. The DimIndustries table is a dimensional table which contains filtering features for our "Fact-" table. 

Files available:

1. DimDictionary.csv
2. DimIndustries.csv
3. FactDataSet.csv

As we have all the required data clean and arranged, we can jump right in to Power BI.

### Loading Files

After loading the data to Power BI we encounter our first "problem", the DimDictionary table doesn't have the correct colum headers. 

<div align="center">
    <img src="https://i.ibb.co/1L9KqHN/1-PBI.png">
</div>

This is very simple to solve, I'm going to promote the correct row to column header using the Power Query Editor.

<div align="center">
    <img src="https://i.ibb.co/CvNhxB9/2-PBI.png">
</div>

Still, there's no way to make a relationship between the DimDictionary and the FactDataSet because we don't have a "NEW CODE" or "OLD CODE" column in the Fact table. The thing is, these codes are in the column header of the table, so there's is no way to relate them directly since Power BI uses a "column query" logic instead of a "row query" logic.

<div align="center">
    <img src="https://i.ibb.co/nB52VHQ/4-PBI.png">
</div>

The lack of a relationship between this two tables is not a problem, since the only thing we want to do with the DimDictionary is to display the information in a Power BI table for reference to the viewer. 

So our model is completed, we have a pretty basic Star Schema plus an unrelated table "DimDictionary".

V1.
----------------------------------------