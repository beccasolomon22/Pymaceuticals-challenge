# Pymaceuticals-challenge

## Sources

1. Starter Code provided in the asssignments file
2. Stack Overflow was a great help when experiencing error messages
3. I occasionally used Chat GPT to help edit code to fix errors
4. Assignment description

# Project Overview as Described in Assignment:

You've just joined Pymaceuticals, Inc., a new pharmaceutical company that specializes in anti-cancer medications. Recently, it began screening for potential treatments for squamous cell carcinoma (SCC), a commonly occurring form of skin cancer.

As a senior data analyst at the company, you've been given access to the complete data from their most recent animal study. In this study, 249 mice who were identified with SCC tumors received treatment with a range of drug regimens. Over the course of 45 days, tumor development was observed and measured. The purpose of this study was to compare the performance of Pymaceuticals’ drug of interest, Capomulin, against the other treatment regimens.

The executive team has tasked you with generating all of the tables and figures needed for the technical report of the clinical study. They have also asked you for a top-level summary of the study results.

## Prepare the Data: 

Imported all dependencies and imported the data from csv's to dataframes. Then merged the mouse data and study results on the Mouse ID into a single dataframe. Then, determined the number of unique Mouse ID's in the dataframe and find any duplicate rows. I then dropped the rows associated with the duplicate Mouse ID. Lastly, confirmed the correct data had been dropped by displaying the new number of unique Mouse IDs.

## Generate Summary Statistics:

Two different methods were used to generate the Mean, Median, Variance, Standard Deviation, and SEM for each of the different drug regimens.

1. Individually:
  - Grouped the dataframe by Drug Regimen
  - Calculated the Mean of the Tumor Volume
  - Calculated the Median of the Tumor Volume
  - Calculated the Variance of the Tumor Volume
  - Calculated the Standard Deviation of the Tumor Volume
  - Calculated the SEM of the Tumor Volume
  - Concatted the five separate dataframes into one
  
2. Using Aggregation:
  - Grouped the Dataframe by Drug Regimen and used the aggregation method to produce the summary statistics all in one line of code

## Create Bar Charts and Pie Charts:

### Bar Charts:

Generated a Bar Chart to show the total number of timepoints for all of the mice tested based on Drug Regimen. This was done using two different methods: pandas and pyplot plotting.

### Pie Charts:

Generated a Pie Chart to show the percentage of Male vs Female mice tested for the entire study. This was done using two different methods: pandas and pyplot plotting.

## Calculate Quartiles, Find Outliers, and Create a Box Plot:

Calculated the final tumor volume of each mouse for the four most promising treatment regimens: Capomulin, Ramicane, Infubinol, and Ceftamin. This was done by first finding the last timepoint for each Mouse ID and creating a dataframe of the Mouse ID and final timestamp then merging that with the original dataframe to get all columns for those Mouse IDs and Timestamps. (An extra step I took was actually dropping all rows that had a different Drug Regimen then the specified four, but the next step involved looking at the dataframe by the specific regimens anyway.)

Then, I created a variable to hold a list of the four Drug Regimens to take a look at and a variable to hold an empty list for the final tumor volumes for each drug. A for loop was used to iterate through each drug, create a variable to hold the dataframe of just that drug, and then create a list of all the final tumor volumes. I then calculated all the quartiles, interquartile range, upper/lower bounds, and outliers. Lastly appended the empty volume list with the list of volumes for each drug.

Finally, generated the box plot for each of the four Drug Regimens using the list of treatments and the list of volumes.

## Create a Line Plot and a Scatter Plot:

Using one of the Mouse IDs that used capomulin, I used the one that has the highest value count in the dataframe for most data, I generated a line plot for the tumor volume vs the timepoint to show the progression of the tumor over the course of the study with treatment. There was a clear downward trend in the amount of time being treated and the volume of the tumor.

For the scatter plot, I found the average tumor volume vs mouse weight for the mice that were treated with capomulin. I started by creating a grouped dataframe that used the aggregation method to calculate the average tumor volume and weight of each mouse. Using that new dataframe, I generated the scatter plot.

## Calculate Correlation and Regression

The average tumor volume and weight of each mouse showed a correlation between both factors of 0.84. Therefore the Tumor volume versus the Weight of the mouse demonstrates a strong correlation. This correlation is visually represented by the linear regression on the scatter plot.

## Conclusions
1. There is a strong correlation between the volume of a tumor and the weight of the mouse.
2. Some Drug Regimens seem to be more effective at lessening the volume of a tumor than others. 
3. Of the four Drug Regimens used in the box plots, capomulin and ramicane appeared to lead to less volume in the tumor.
