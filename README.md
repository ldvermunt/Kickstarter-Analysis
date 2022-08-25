# Kickstarting with Excel

## Overview of Project

### The purpose of this project is to gain insight into how Excel can be used to turn raw data into deliverable conclusions.  The hypothetical presented is based around a hopeful theatre producer wanting to fund her play for a budget of $10,000 in late spring.  The data was presented in spreadsheet format, and consists of thousands of former crowdfunded "Kickstarter" campaigns in the arts. This information was used to focus on two specific questions.
### - How were the camapign outcomes affected by its launch date?
### - How were the campaign putcomes affected by the dollar amounts of their goals?

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
- With this data available a line chart is created to display the relationship between the dollar amounts and percentage success of the Kickstarter campaigns for plays.
![image](https://user-images.githubusercontent.com/111530580/186726934-77de7849-da12-4b44-89a2-5a4fed966648.png)



### Challenges and Difficulties Encountered
-Presenting this data required first modifying the data set in order to display it in an understandable format.  Changing Unix to mm/dd/yyyy requires a manually enterd formula, rather than one already included in Excel.
-Using a "COUNTIFS" function broke down our data into manageable sections, howeverm it is important to thoroughly review your formula to ensure no data is excluded that you are looking to isolate.   

## Results

- Conclusions, limitations and suggestions about the Outcomes based on Launch Date?
	- The first and most obvious outcome from the "Launch Date" data is that a higher likelyhood of success is favored during late spring / early summer.  Paticularly May - June.
	- It is also notable that although the "Outcomes Based on Launch Date" chart is indicitive of the May/June uptick, the difference is not as stark as it first appears.  Based on percentage success rate, the "worst " month, October has ony a 5.5% lower success rate than the "best" month, May.  Without this additional data, a cursory look at the chart could lead one to believe May's rate of success is double that of October's.  The percentages help to put the raw numbers chart into better perspective as shown here:
![image](https://user-images.githubusercontent.com/111530580/186732791-4afebeb5-e184-491c-bf79-c016d9cc09af.png)


- Conclusions, Limitations and suggestions about the Outcomes based on Goal?
	- The outcomes based on goal chart has data that varies widely, from aa 100% failure rate in the "$45,000 to $49,999" category to only a 30% failure rate in the "less than $1000" category.  
	- This data requires some closer examination.  If one takes tha mean and average of the success rate, the result is 56.5.  The mean however for the same data is only 6.5.  This indicated that the data is skewed left. 
	- Closer inspection reveals that only one campaign was attempted in the "$45,000 to $49,999" range.  Not enough to include it in a meaningful analysis.  The data breaks down as follows:
	![image](https://user-images.githubusercontent.com/111530580/186739944-d7f5a394-208c-4a3f-8481-691d37ec7c61.png)

	-If one uses the IQR method to determine the outliers in the "successful campaigns" categry, then more than half of the data is considered an outlier.
	
	-Since our fictional playwrite was going to budget for $10,000 I created another chart with a dollar range closer to hher stated amount:
	
	![image](https://user-images.githubusercontent.com/111530580/186747608-ed756436-65d3-451f-8c1e-869acd283047.png)

	-The same limitations occured here, however as the more limited data caused a similar amount of outliers.
	
	-A final conclusion about the data based on goal amounts is that it does not lend itself to a meaningful conclusion about the relationship between amounts and success rate.

	
