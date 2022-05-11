# Requirements
1. When the app is started, the user is presented with the main menu, which allows the user to do one of the following:
    1. Enter or edit current job details
       > We added the 'Job' class which contains an 'editCurrentJob()' operation.
    2. Enter job offers
       > The 'Job' class also contains an 'addJobOffer()' method. The 'isCurJob' boolean in the 'Job' class distinguishes between a current job and a job offer.
    3. Adjust the comparison settings
       > We created a 'ComparisonSetting' class which contains an 'adjustComparisonSetting()' operation.
    4. Compare job offers (disabled if no job offers were entered yet).
       > We added a 'ComparisonTable' class with the 'comparison()' method that accepts two 'Job' objects as parameters.
2. When choosing to enter current job details, a user will:
    1. Be shown a user interface to enter (if it is the first time) or edit all of the details of their current job, which consist of:
       > The user interface will be handled with the GUI implementation. The following attributes were added to the 'Job' class:
         1. Title
        2. Company
        3. Location (entered as city and state)
        4. Cost of living in the location (expressed as an index)
        5. Yearly salary
        6. Yearly bonus
        7. Allowed weekly telework days (expressed as the number of days per week allowed for remote work, inclusively between 0 and 5)
        8. Retirement benefits (as percentage matched)
        9. Leave time (vacation days and holiday and/or sick leave, as a single overall number of days)
    2. Be able to either save the job details or cancel and exit without saving, returning in both cases to the main menu.
       > The 'editCurrentJob()' method handles editing and saving the current job. The cancel and exit functionality are related to the GUI implementation.
3. When choosing to enter job offers, a user will:
    1. Be shown a user interface to enter all of the details of the offer, which are the same ones listed above for the current job.
       > The 'Job' class contains all the details necessary. The user interface will be handled with GUI implementation.
    2. Be able to either save the job offer details or cancel.
       > This can be handled with the 'addJobOffer()' operation in the 'Job' class.
    3. Be able to (1) enter another offer, (2) return to the main menu, or (3) compare the offer with the current job details (if present).
       > Entering another offer can be handled with the 'addJobOffer()' method, and comparing the offer with the current job is handled by the 'comparison()' operation in the 'ComparisonTable' class.
4. When adjusting the comparison settings, the user can assign integer weights to:
   > We added the following Integer type attributes to the 'ComparisonSettings' class with a default value of 1:
    1. Yearly salary
    2. Yearly bonus
    3. Allowed weekly telework days
    4. Retirement benefits
    5. Leave time  
       If no weights are assigned, all factors are considered equal.
5. When choosing to compare job offers, a user will:
    1. Be shown a list of job offers, displayed as Title and Company, ranked from best to worst (see below for details), and including the current job (if present), clearly indicated.
       > We added the 'JobList' class which is an aggregation of the 'Job' class. This class also contains the 'rankList()' operation which returns the sorted list of jobs. 
    2. Select two jobs to compare and trigger the comparison.
       > This can be handled by the 'comparison()' and 'select()' operations of the 'ComparisonTable' class.
    3. Be shown a table comparing the two jobs, displaying, for each job:
       > This can be handled by the 'ComparisonTable' class 'comparison()' method.
        1. Title
        2. Company
        3. Location
        4. Yearly salary adjusted for cost of living
        5. Yearly bonus adjusted for cost of living
        6. Allowed weekly telework days
        7. Retirement benefits (as percentage matched)
        8. Leave time
    4. Be offered to perform another comparison or go back to the main menu.
       > This can be handled by the 'comparison()' operation. Navigating back to the main menu will be part of the GUI implementation.
6. When ranking jobs, a job’s score is computed as the weighted sum of:
   > We added the derived 'jobScore', 'salaryAdjusted', and 'bonusAdjusted' attributes to 'Job' class. The 'jobScore' is determined via the 'calculateScore()' method which we added to 'JobList'. This operation calculates scores for all jobs at once using the current comparison settings and is thus dependent on the 'ComparisonSetting' class. The 'salaryAdjusted' and 'bonusAdjusted' variables are calculated in the 'ComparisonTable' class.

   `AYS + AYB + (RBP * AYS) + (LT * AYS / 260) - ((260 - 52 * RWT) * (AYS / 260) / 8)`

   Where:
    - AYS = yearly salary adjusted for cost of living
    - AYB = yearly bonus adjusted for cost of living
    - RBP = retirement benefits percentage
    - LT = leave time
    - RWT = telework days per week

   The rationale for the RWT subformula is:
    1. Value of an employee hour = (AYS / 260) / 8
    2. Commute hours per year (assuming a 1-hour/day commute) = `1 * (260 - 52 * RWT)`
    3. Therefore travel-time cost = `(260 - 52 * RWT) * (AYS / 260) / 8`    
       For example, if the weights are 2 for the yearly salary, 2 for the retirement benefits, and 1 for all other factors, the score would be computed as:  
       `2/7 * AYS + 1/7 * AYB + 2/7 * (RBP * AYS) + 1/7 * (LT * AYS / 260) - 1/7 * ((260 - 52 * RWT) * (AYS / 260) / 8)`
7. The user interface must be intuitive and responsive.
   > This is not represented, as it will be handled within GUI implementation.
8. For simplicity, you may assume there is a single system running the app (no communication or saving between devices is necessary).
   > This is not represented, as it will be handled within system implementation.

