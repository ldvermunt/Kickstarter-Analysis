# Kickstarting with Excel

## Overview of Project

### The purpose of this project is to gain insight into how Excel can be used to turn raw data into deliverable conclusions.  The data was presented in spreadsheet format, and consists of thousands of former crowdfunded "Kickstarter" campaigns in the arts. This information was used to focus on two specific questions.
- How were the camapign outcomes affected by its launch date?
- How were the campaign putcomes affected by the dollar amounts of their goals?

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
- The data for launch date was offered in Unix Time Code.  First a conversion had to be performed to alter it into a user friendly format.

The "Launched_at" column which looked like this:  ![image](https://user-images.githubusercontent.com/111530580/186700413-f6e2e578-f2e6-4d89-9c59-2f3c9f14ec44.png)  Was converted to this:  ![image](https://user-images.githubusercontent.com/111530580/186703519-5f374eca-7ac5-4f45-9c78-53e219d8a3eb.png)
Using the formula: =(((J2/60)/60)/24)+DATE(1970,1,1) - Where J2 was the Unix data, or 1434931811.  This was then applied to the entire column.

- Next we needed to isolate the year from the new "Date Created Conversion" column.  This was achieved by using the formula =YEAR(S2) where S2 is the MM/DD/YYYY formatted cell.  This was then applied to the entire column.

- Then a Pivot Table was created.  The parameters were chosen to isolate the months along the X-axis, and outcome numbers aling the Y-axis, and filterable by "Parent category" and "Years". 

![image](https://user-images.githubusercontent.com/111530580/186707650-58735ae3-283a-40c6-8622-dbf9ed443763.png)

- A line chart was created from this data.
![image](https://user-images.githubusercontent.com/111530580/186710449-002da533-54d6-41b9-8b13-1d394fb8b611.png)


### Analysis of Outcomes Based on Goals
- In order to isolate the data to display different outcomes based on goals a new sheet was created to break down the following categories in dollar amounts:

![m1-challenge-bullet-3](https://user-images.githubusercontent.com/111530580/186711495-87f8d6c3-d70b-4e2e-8c7b-abece3489c7b.png)

- The data needed to be further broken down into more relevant data pieces.  Columns were created as such:
						
![image](https://user-images.githubusercontent.com/111530580/186713581-5eb98f6f-358f-47a8-8dc4-ea463659c0e8.png)

- Then a "COUNTIFS" function was added to the empty sells in order to display the data we were looking for.  The relevancy was increased by including only plays in our data.  For example, the formula in the cell intersecting "1000 to 4999" and "Number Successful" was: =COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$R:$R,"plays",Kickstarter!$D:$D,"<5000",Kickstarter!$F:$F,"successful")

- The totals and percentages were inputted using mathematical formulas for "SUM" and dividing and multiplying as necessary.


### Challenges and Difficulties Encountered

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
