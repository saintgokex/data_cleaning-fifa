# data_cleaning-fifa
This is the step-by-step documentation of data cleaning process of fifa dataset
### Hi Data Enthusiast! My name is Abdulhameed Jamiu and this is my complete step-by-step documentation of the cleaning process of fifa dataset using power query of power BI
Selected all columns and then I applied trim function to trim the table
Split contract into two columns – contract_start and contract_end. There are errors as a result of loan end dates input in this column, I turned them all to null since there’s a separate column for the players on loan
Height column – duplicated the column, then I created a conditional column to separate the height in feet from the ones in cm, I then splited the height ft column by delimiter to separate feet from inches then I multiply the feet column by 12. I then created a custom column to add the two columns together. To convert the inches column to cm, I multiplied it by 2.54.
Height – copy – this is the original height column I duplicated, I converted data type to number and replaced errors with null values and then merged the two columns together into a new column named “New Height (cm)”
Weight – this column has two units – lbs and kg. I duplicated the column and created a conditional column for values ending with Ibs. I replaced lbs with null and divided the column by 2.205 to convert Ibs to kg.
I created another conditional column for values ending with kg, I replaced kg with null changed data type to decimal and merged the two columns into a new column called “New Weight (kg)
Change the format of column Loan Date End from text to date
Duplicated values columns twice, renaming both to value in Million and value in thousands
Extract text between delimiters € and M for value in million and € and K for value in thousands.
Sorted the column value in thousand in descending order such that values in millions will be displayed first, then I changed text type to decimal number such that values with M at the end return an error. Then I multiplied the column by 1000
I replaced all errors with null.
Sorted the column value in million in descending order such that values in thousand will be displayed first, then I changed column type to decimal number such that values ending with k will return an error. Then I multiplied the column by 1000000
I then merged the two columns together to create a new column called New Value
For column wage, I duplicated the column twice and renamed each to wage – hundred and wage – thousand
For column wage – hundred. I extracted value before delimiter € such that I’m left with values in hundred and thousand (ending with k). I changed data type to decimals such that values ending with k returned error. Replaced errors with null.
For column wage – thousand, I added a custom function to check wage – thousand column and see if the cell ends with K and that the custom function should add the value in the new column. Then I extract the value between delimiter € and K, then I multiply the value by 1000. Replaced errors with null
For release clause, I created a conditional column to put values that end in M in a column, those that ends in K in another column and those that don’t end with either in a separate column.
Column with million – I extracted text between delimiters € and M, changed text type to decimal and I multiplied by 1000000
Column with thousand – I extracted text between delimiters € and K, changed text type to decimal and I multiplied by 1000
Column with no letter, I extracted texts after delimiter €, converted to text and since the column comprises just €0 and null values, I didn’t perform any further operation.
I merged all the three columns after each has been carefully cleaned, then I changed the data type to fixed decimal number and renamed it New Release Clause (€)
For column W/F, IR and SM, I replaced the star at the end of every value with null and renamed the column to W/F Rating, IR Rating and SM Rating respectively and I changed their formats to whole number
Find the cleaned dataset here 
