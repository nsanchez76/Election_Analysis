# Election_Analysis

## Project Overview

The purpose of this analysis was to complete the audit of a recent Colorado congressional election. In particular, the audit included:

  1. A calculation of the total number of votes cast.
  2. A breakdown of the number of votes from each county.
  3. A calculation of the percentage of the total votes coming from each county.
  4. A determination of the county that had the largest turn out.
  5. A complete list of candidadtes who received votes.
  6. A calculation of the total number of votes each candidate received.
  7. A calculation of the percentage of votes each candidate won.
  8. A determination of the winner of the election based on the popular vote.
  
## Resources

- Data Source: "election_results.csv"
- Software: Visual Studio Code v. 1.68.1, Python Extension v2022.8.0, Python Launcher 3.10.5

## Coding Methods

 - The total number of votes was calcuated using a "for" loop that added one to the counter as it cycled through the rows 
   of the .csv file: 
      
        "for row in reader:
            total_votes = total_votes + 1"

- Each county's votes were tallied using an "if" statement. As the rows in the .csv were read, the county name was checked. 
  If it was not in the "county_options" list, it was added to the list. In addtion, each county's votes were summed and stored in   the "county_votes" dictionary (a similar method was used to tally the number of votes each candidate received):

      "if county_name not in county_options:
            county_options.append(county_name)
            county_votes[county_name] = 0
        county_votes[county_name] += 1"
        
 - Another "if" statement was used to determine the cunty with the largets turn out (a similar method was used to determine 
    the winner of the election:
    
        "if (cvotes > largest_turnout) and (cvote_percentage > largest_percentage):
            largest_turnout = cvotes
            largest_county = county_name
            largest_percentage = cvote_percentage"
            
  

## Results

The analysis of "election_results.csv" is as follows:

- There were 369,711 total votes cast in the election.

- Each counties votes were:
  - Jefferson: 10.5% (38,855 votes)
  - Denver: 82.8% (306,055 votes)
  - Arapahoe: 6.7% (24,801 votes)
  
- The county with the largest turn out was Denver.

- The candidates were:
  - Charles Casper Stockham
  - Diana DeGette
  - Raymon Anthony Doane
  
The candidates' results were:
  - Charles Casper Stockham received 23.0% of the vote with 85,213 votes.
  - Diana DeGette received 73.8% of the vote with 272,892 votes.
  - Raymon Anthony Doane received 3.1% of the vote with 11,606.
  
The winner of the election was:
  - Diana DeGette who received 73.8% of the vote with 272,892 votes.

A screen shot of the output file is below:

<img width="852" alt="Election_Analysis" src="https://user-images.githubusercontent.com/106849689/177016126-aea8332b-ba46-4666-b7c6-698d946daaa7.png">

A screen shot of the terminal output is below:

<img width="721" alt="Terminal_Election_Analysis" src="https://user-images.githubusercontent.com/106849689/177016226-bfc6336f-c109-4c86-8f1d-12a485f4509a.png">


## Election Audit Summary

The "PyPoll_Challenge.py" script is extremely versatile. It can be used in any election, provided that the raw data is
formatted similar to the "election_results.csv" file. An improvement to the script could be to try to eliminate some of the
variables. For example, the "candidate_options[]" and the "candidate_votes{}" may not both be necessary. The same goes for the
"county_options[]" and "county_votes{}". Another potential improvement would be to move all of the code pertaining to the
counties to one section of the file, and all the code for the candidates to another part of the file. This would help make the
script more modular and less prone to mistakes.
