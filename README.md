# Election_Analysis

## Purpose

The purpose of this project was to write an automated code in python that can be used to prepare an 
election audit to certify the election results based on the popular vote for American congressional 
and senatorial districts, and American local elections.

In this project, an election audit was performed for the congressional precinct of Colorado using 
the tabulated vote results presented in a csv file. Using python, a script was written to collect
the total number of votes cast, the votes and vote percentage of each candidate, the count and 
percentage of voter turnout for each county, including determining the county with the largest
turnout and finally the election winner. The python script was written, executed and 
saved in VS Code.

### Project Overview
A Colorado Board of Elections employee has listed the following tasks to complete the auction audit of a recent local congressional election.

1. Calculate the total number of votes cast.
2. Get a complete list of candidates who recieved votes.
3. Calculate the total number of votes each candidate received.
4. Calculate the percentage of votes each candidate won.
5. Determine the winner of the election based on popular vote.

The election commission requested additional information on the votes for each county to complete the audit. The following tasks were completed add this information to the audit. 

1. Get a list of the counties in the congressional precinct. 
2. Calculate the total number of votes from each county.
3. Calculate the percentage of votes from each county.
4. Determine the county with the highest voter turnout.

## Election Results

### Audit Results

INSERT IMAGE

The analysis of the election show that:
* There were **369, 711** votes cast in the election.

* The counties in the congressional precinct were:
  * Jefferson
  * Denver
  * Arapahoe

* The county results were:
  * Jefferson county had 10.5% of the vote and 38855 number of votes.
  * Denver county had 82.8% of the vote and 306055 number of votes.
  * Arapahoe county had 6.7% of the vote abd 24801 number of votes.
* The county with the greatest number of votes is **Denver**, which had the highest voter turnout at 82,8% with 306055 votes. 

* The candidates were: 
  * Charles Casper Stockham
  * Diana DeGette
  * Raymon Anthony Doane
* The candidate results were:
  * Charles Casper Stockham received 23.0% of the vote and 85,213 number of votes.
  * Diana DeGetter received 73.8% of the vote and 272,892 number of votes.
  * Raymon Anthony Doane received 3.1% of the vote and 11,606 number of votes.
* The winner of the election was:
  * **Diana DeGette** who received 73.8% of the vote and 272,892 number of votes.
  
### Audit Summary

The election audit script presented in this project can be utilized in other forms of elections with slight modifications. For the script to execute successfully, the tabulated data of votes must be in csv format. The code grabs the vote count, candidate name and county name from row indexes 0, 1 and 2 of the csv data. The codes assumes that all csv voting data will be organized in this order. To prevent misread row information, a code can be added to print the row headers in the terminal. If any of the rows in the csv file are not in the order assumed by the code, the index number used to retrieve the vote count, candidate name and county name can be changed to match the correct row. 
The print code would be written underneath the following code in the script:
header = next(reader)
print(header) 

Another potential modification is renaming the county variables. County variables such as county_list and county_votes can be renamed accordingly to match the electoral district being used to group and count the votes. Using the find and replace function in the code editor, all instances of the specific variable will be replaced with the new appropriate variable name. In Vs Code, this can be achieved using CTRL + H or clicking on the Edit tab on the top ribbon and select Replace from the scroll down menu.

IMAGE

As voting data is sensitive and extremely important, maintaining the structure of the code is also extremely important. Converting the list of candidates and counties into tuples after collecting all the unique values through the code will add an extra layer of protection against any changes that may happen elsewhere in the code if more modifications occur. 

The covert to tuple code would follow after all the unique values were appended to the candidate and county list. 

# If the candidate does not match any existing candidate add it to the candidate list
        if candidate_name not in candidate_options:

            # Add the candidate name to the candidate list.
            candidate_options.append(candidate_name)

            # And begin tracking that candidate's voter count.
            candidate_votes[candidate_name] = 0

    candidate_options = tuple(candidate_options)
    print(candidate_options)

