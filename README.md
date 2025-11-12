# Loan-Data-Cleaning-and-Preprocessing
Udemy Course project - Cleaning and Preprocessing loan data
Project completed fully in Python using the NumPy and Pandas packages

This course was interesting, and while this was mostly a code-along I learned how to break things down and take a step at a time and understand thought process for what data we want

Imported csv file and checked for any incomplete data
- Ceated 2 temporary values for numeric columns, created a Max + 1( temp_fill)  and an average (temp_mean) filler
- the temp_fill is to see where there is missing value in the dataset
- The temp_mean filler stores the mean for every column
- created a temporary stats variable to house MIN, AVG, MAX values
Split the dataset into Numeric and String columns

Checkpoint creation

Started working with the String columns, 
Went column by column to see what needs to be changed or altered if required.
- Issue Date - Stripped the year from the date as we are only working with 1 specific year, 2015
    - Altered the column data from Month to instead show the month as the numeric value ( 1 - 12)
    - Blanks set to 0 - we will address this issue later in the numeric columns section
- Loan Status - Seperating the fields into "good" and "bad" statuses, blanks were set as bad status
- Term - Renamed column and altered data to exclude the month wording as the terms is always displayed over months, also set Blank fields to be worst case ( 60 months)
- Grade and Subgrade - Both columns not needed, removed the Grade column and filled blanks in Sub_Grade column as "H1"
- Verification status - Set to "good" and "bad" statuses
- URL - Stripped most of the URL to see if the ID at the end matches the user ID column. It does and I have deleted the URL column.
-  State Address - Ran query to see which states we have and how many entries each.
    - Noticed that there is one state missing, I believe it is Idaho,  and will have missing value return a zero to indicate row entry is part of missing state.
    - Placed all states into 4 dictionaries, depending on region(West, south, Midwest, east) and ran code to indicate which region the row entry belongs to more easily.

Created another checkpoint

Numeric columns, followed the same logic of going column by column to see what may or may not need to be adjusted.
- ID - Looked for any blank values by using the temp_fill value - no blanks detected
- Funded Amount - Replaced any temp_fill values with the max value
- Loaned Amount, INterest Rate, Total Payment, Installment - same process as funded amount, used a for loop to write for all 4 columns at once

Imported new CSV file with exchange rates EUR-USD

- Created a new column into the dataset to show the exchange rates for the different months and set the month "0" to be the average EUR-USD exchange rate
    - Had to reshape the new column to be 2 dimensional in order to stack and concat onto the dataset
- From USD to EUR - Extended the columns to include to show the difference after the exchange rate is applied
- Reordered the headers to make more sense
- Interest Rate - slight adjustment to how value will be calculated

Created Checkpoint

Completing the dataset - we split the dataset into 2 parts, strings and numeric. Now were join them together again.

Save the Dataset

