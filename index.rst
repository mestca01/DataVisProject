.. Speed Dating Project documentation master file, created by
   sphinx-quickstart on Tue Nov 27 09:37:40 2018.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

.. toctree::
   :maxdepth: 2
   :caption: Contents:


# What is the Secret to Getting the Second Date?
***What influences love at first sight? (Or, at least, love in the first four minutes?)***

### Introduction:

* Data was gathered from 552 participants in experimental speed dating events from 2002-2004.

* This experiment was created by Columbia Business School professors Ray Fisman and Sheena Iyengar for their paper *Gender Differences in Mate Selection: Evidence From a Speed Dating Experiment*.

* During the events, the attendees would have a four minute "first date" with every other participant of the opposite sex.

* At the end of their four minutes, participants were asked if they would like to see their date again. They were also asked to rate their date on six attributes:
    * **Attractiveness**
    * **Sincerity**
    * **Intelligence**
    * **Fun**
    * **Ambition**
    * **Shared Interests**
    
* The dataset also includes questionnaire data gathered from participants at different points in the process. These fields include:
    * Demographics
    * Self-Perception Across Key Attributes
    * Beliefs on What Others Find Valuable in a Mate
    * Lifestyle Information
    
    
    
    
    
### Cleaning the data:
   Although we originally thought that having multiple rows represent one individual would cause problems, we discovered that it was actually beneficial to the accuracy of our data.  The advantage of having multiple rows for each individual participant is that we can get multiple opinions on an individual’s attributes instead of just one.  This allows for more accurate results.
   
   However, we discovered that there were some columns and rows that could have possibly affected our results negatively.  We decided to take out columns that were missing large amounts of data and were not that important for the question that we were asking (the data set contains 190 columns, so we were not very worried about taking some out).  We took out these columns in python using “iloc” to select our columns and “concat” to put all of them together into a new data frame.  This allows us to go back and add any columns that we took out in case we needed them in the future.  Taking these columns out in Excel, or directly from the csv, would permanently delete these columns, not allowing us to add any of the columns back if we needed them.  It also allows us to use pandas’ “dropnas” without deleting rows that have N/As in columns that we do not need.
   
   We also discovered that one of the speed dating waves, wave 12, would affect our data negatively.   This particular wave had a certain restriction that was inconsistent with the rest of our data.  In this wave, the participants were only allowed to say yes to a second date to 50% of their dates.  We decided that these rows risked affecting our results negatively.  Since we have thousands of observations in this data set anyway, we decided that it would be beneficial to our analysis if we removed wave 12 from our data frame.
