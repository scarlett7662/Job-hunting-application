# Test Plan
#### V3: Updated plan with final results
#### V2: Updated 3/10/21 to fix calculation which was based on wrong requirement doc
**Author**: Mallorie Winkler (Team 004)

## 1 Testing Strategy

### 1.1 Overall strategy

Tests will be implemented and conducted throughout the development process. The Test Manager will maintain the table of test cases and developers will also contribute to test design. Our testing will involve unit, integration, system and regression testings as follows: 
- **Unit Tests**:
  - Each new or changed method within a class will have a corresponding unit test done via JUnit.
  - Method behavior is tested with sufficient valid, invalid, and/or empty inputs to validate correct method behavior and return high code coverage. 
  - Unit tests should be run and passed prior to moving forward to integration tests.  
- **Integration Tests**:
  - These tests validate the behavior of a combination of units and will also be done with JUnit.
  - Mocking of the database may be necessary.
- **System**: 
  - System tests will validate the app as a whole and will be automated via Espresso.
  - Some manual system testing may also take place.
  - System tests should validate both functional and non-functional requirements which are detailed in ExtraRequirements.md. 
  - These tests should run following the successful completion of unit and integration tests.
- **Regression**: 
  - Regression testing will be as automated as possible and will re-use our test suite.
  - The complete test suite should run after the addition of any new features or any other substantial changes.


Following Android standards, unit tests which can be run on the local machine will be stored in a 'test' directory. The 'androidTest' directory will contain all other component, integration and system tests which may need to run on an Android virtual device or a real device if available.
### 1.2 Test Selection

The unit and integration tests will utilize a combination of White and Black-Box testing techniques. White-Box test case selection will require code coverage techniques, namely Branch and Condition Coverage. 
Black-Box tests will rely on specification (method signatures) to test a variety of inputs and thus exercise and validate correct method behavior. 
Partition Testing and Boundary Values will be used in partitioning and selecting appropriate test inputs for all tests. 
System tests will be determined following the Finite State Machine model in which we think of all the possible states and transitions of our system. These System tests will focus on navigation through the app and should validate the expected appearance of the UI.
Finally, regression testing will reuse these above tests/techniques.
  
### 1.3 Adequacy Criterion

Test cases should generally satisfy criteria such as being traceable to requirements, simple and clear, and clear in expected results.
Functional coverage is another metric we may use as a criteria for adequacy. This calculates the percentage of test cases to their related functions.
We will use structural coverage as the main metric for measuring adequacy, however. Android Studio allows you to "Run Tests with Coverage," which outputs code coverage metrics.
A typical coverage target (for statement coverage) is 80-90%.
### 1.4 Bug Tracking

To track bugs and issue requests, we will use the Github Issue tracker.
### 1.5 Technology

We intend to use the following technology:
- JUnit: Unit and Integration testing
- Espresso: System testing (UI testing)

## 2 Test Cases

The app was tested both manually and via automated Espresso tests and JUnit tests. The tests were also run on several devices:
- Emulated Devices: Galaxy Nexus API 28, Pixel XL API 30, Nexus 4 API 30, various others
- Physical Device: Nokia 2.4 Android 10 OS

| Test Case | Purpose | Steps  | Expected Result|  Actual Result | Pass/Fail? |
|-----------|-------|-----------------|------------------|----------------|--------------|
|1. | *Current Job* 'title' input is non-empty on save| 1. Navigate to *Current Job* screen<br />2.Enter all job details and empty string for 'title'<br /> | Expect an "invalid" notification or pop up on text field and inability to save| Invalid pop up | Pass |
|2. | *Current Job* 'company' input is non-empty on save | 1. Navigate to *Current Job* screen<br />2.Enter all job details and empty string for 'company'<br /> | Expect an "invalid" notification or pop up on text field | Invalid pop up | Pass |
|3. | *Current Job* 'location' input is non-empty on save | 1. Navigate to *Current Job* screen<br />2.Enter all job details and empty string for 'location' (city)<br /> | Expect an "invalid" notification or pop up on text field | Invalid pop up | Pass |
|5. | *Current Job* 'cost of living' input is non-empty on save | 1. Navigate to *Current Job* screen<br />2.Enter all job details and except for 'cost of living'<br /> | Expect an "invalid" notification or pop up on text field | Invalid pop up | Pass |
|6. | *Current Job* 'yearly salary' input is non-empty on save | 1. Navigate to *Current Job* screen<br />2.Enter all job details and except for 'yearly salary'<br /> | Expect an "invalid" notification or pop up on text field | Invalid pop up | Pass |
|7. | *Current Job* 'yearly bonus' input is non-empty on save | 1. Navigate to *Current Job* screen<br />2.Enter all job details and except for 'yearly bonus'<br /> | Expect a "invalid" notification or pop up on text field | Invalid pop up | Pass |
|8. | *Current Job* 'allowed weekly telework days' input is non-empty on save | 1. Navigate to *Current Job* screen<br />2.Enter all job details and except for 'allowed weekly telework days':<br /> | Expect a "invalid" notification or pop up on text field | Invalid pop up | Pass |
|9. | *Current Job* 'allowed weekly telework days' input contains an integer between 0 and 5 | 1. Navigate to *Current Job* screen<br />2.Enter all job details and -1 for 'allowed weekly telework days':<br /> | Expect a "invalid" notification or pop up on text field |Invalid pop up | Pass|
|10. | *Current Job* 'allowed weekly telework days' input contains an integer between 0 and 5 | 1. Navigate to *Current Job* screen<br />2.Enter all job details and 6 for 'allowed weekly telework days':<br /> | Expect a "invalid" notification or pop up on text field | Invalid pop up | Pass |
|11. | *Current Job* 'retirement benefits' input is non-empty on save | 1. Navigate to *Current Job* screen<br />2.Enter all job details and except for 'retirement benefits'<br /> | Expect a "invalid" notification or pop up on text field | Invalid pop up | Pass |
|12. | *Current Job* 'leave time' input is non-empty on save | 1. Navigate to *Current Job* screen<br />2.Enter all job details and except for 'leave time'<br /> | Expect a "invalid" notification or pop up on text field |Invalid pop up | Pass |
|13. | *Current Job* 'cost of living' input is non-empty on save | 1. Navigate to *Current Job* screen<br />2.Enter all job details and except for 'cost of living':<br /> | Expect a "invalid" notification or pop up on text field |Invalid pop up | Pass|
|14. | *Job Offer* 'title' input is non-empty on save| 1. Navigate to *Job Offer* screen<br />2.Enter all job details and empty string for 'title'<br /> | Expect an "invalid" notification or pop up on text field and inability to save|Invalid pop up | Pass |
|15. | *Job Offer* 'company' input is non-empty on save | 1. Navigate to *Job Offer* screen<br />2.Enter all job details and empty string for 'company'<br /> | Expect an "invalid" notification or pop up on text field | Invalid pop up | Pass|
|16. | *Job Offer* 'location' (city) input is non-empty on save | 1. Navigate to *Job Offer* screen<br />2.Enter all job details and empty string for 'location' (city)<br /> | Expect an "invalid" notification or pop up on text field | Invalid pop up | Pass |
|17. | *Job Offer* 'location' (state) input is non-empty on save | 1. Navigate to *Job Offer* screen<br />2.Enter all job details and empty string for 'location' (state)<br /> | Expect an "invalid" notification or pop up on text field | Invalid pop up | Pass |
|18. | *Job Offer* 'cost of living' input is non-empty on save | 1. Navigate to *Job Offer* screen<br />2.Enter all job details and except for 'cost of living'<br /> | Expect an "invalid" notification or pop up on text field | Invalid pop up | Pass |
|19. | *Job Offer* 'yearly salary' input is non-empty on save | 1. Navigate to *Job Offer* screen<br />2.Enter all job details and except for 'yearly salary'<br /> | Expect an "invalid" notification or pop up on text field | Invalid pop up | Pass |
|20. | *Job Offer* 'yearly bonus' input is non-empty on save | 1. Navigate to *Job Offer* screen<br />2.Enter all job details and except for 'yearly bonus'<br /> | Expect a "invalid" notification or pop up on text field | Invalid pop up | Pass |
|21. | *Job Offer* 'allowed weekly telework days' input is non-empty on save | 1. Navigate to *Job Offer* screen<br />2.Enter all job details and except for 'allowed weekly telework days':<br /> | Expect a "invalid" notification or pop up on text field | Invalid pop up | Pass |
|22. | *Job Offer* 'allowed weekly telework days' input contains an integer between 0 and 5 | 1. Navigate to *Job Offer* screen<br />2.Enter all job details and -1 for 'allowed weekly telework days':<br /> | Expect a "invalid" notification or pop up on text field | Invalid pop up | Pass |
|23. | *Job Offer* 'allowed weekly telework days' input contains an integer between 0 and 5 | 1. Navigate to *Job Offer* screen<br />2.Enter all job details and 6 for 'allowed weekly telework days':<br /> | Expect a "invalid" notification or pop up on text field |Invalid pop up | Pass |
|24. | *Job Offer* 'retirement benefits' input is non-empty on save | 1. Navigate to *Job Offer* screen<br />2.Enter all job details and except for 'retirement benefits'<br /> | Expect a "invalid" notification or pop up on text field | Invalid pop up | Pass |
|25. | *Job Offer* 'leave time' input is non-empty on save | 1. Navigate to *Job Offer* screen<br />2.Enter all job details and except for 'leave time'<br /> | Expect a "invalid" notification or pop up on text field | Invalid pop up | Pass|
|26. | *Job Offer* 'cost of living' input is non-empty on save | 1. Navigate to *Job Offer* screen<br />2.Enter all job details and except for 'cost of living'<br /> | Expect a "invalid" notification or pop up on text field | Invalid pop up | Pass |
|27. | *Comparison Settings* weight inputs have a default value of 1  | Pre-requisite: Weight settings have not been adjusted <br />1. Navigate to *Comparison Settings* screen <br /> | Expect each input to have a value of 1 | all inputs have value of 1 | Pass |
|28. | *Comparison Settings* weight inputs are non-empty on save  | 1. Navigate to *Comparison Settings* screen<br />2.Remove default or adjusted weight settings <br /> | Expect a "invalid" notification or pop up on text fields | Invalid pop up | Pass |
|29. | Verify that editCurrentJob() accepts a Job object and correctly stores it in the database with isCurJob = true  | 1. Input: job object <br /> 2. Check database  | Expect objects to match and isCurJob = true | Objects match |Pass |
|30. | Verify addJobOffer() accepts a Job object and correctly stores it in the database with isCurJob = false | 1. Input: job object <br /> 2. Check database  | Expect objects to match and isCurJob = false  | Objects match |Pass |
|31. | Verify calculateSalaryAdjusted() returns the correct calculation  | Input: Job object - <br /> 'title': 'Developer'<br />'company': 'Amazon'<br/>'location': 'Berlin', 'Germany'<br /> costOfLiving': 125<br />'yearlySalary': 100000<br />'yearlyBonus': 5000<br />'allowedWeeklyTeleworkDays': 3<br />'retirementBenefits': 0.07<br />'leaveTime': 25<br />'isCurJob': false <br /> 'salaryAdjusted': 0<br />'bonusAdjusted': 0 <br />'jobScore': 0 | Expect 'salaryAdjusted' of object = 100000*(100/125) = 80000  | 80000 | Pass |
|32. | Verify calculateBonusAdjusted() returns the correct calculation|Input: Job object - <br /> 'title': 'Developer'<br />'company': 'Amazon'<br/>'location': 'Berlin', 'Germany'<br />'costOfLiving': 125<br />'yearlySalary': 100000<br />'yearlyBonus': 5000<br />'allowedWeeklyTeleworkDays': 3<br />'retirementBenefits': 0.07<br />'leaveTime': 25<br />'isCurJob': false <br /> 'salaryAdjusted': 0<br />'bonusAdjusted': 0 <br />'jobScore': 0 | Expect bonusAdjusted of object = 5000*(100/125) =  4000  | 4000 |Pass |
|34. | Ensure that adjustComparisonSettings() correctly updates the Comparison Settings | 1. Input 5 integer values: 1, 2, 3, 4, 5 | Expect: 1, 2, 3, 4, 5 | 1,2,3,4,5 | Pass |
|35. | Verify that calculateScore() accepts a list of Jobs and returns the correct score calculation for each |Pre-requisite: Comparison Settings (weights) have default value of 1 <br />  <br /> 1. Input JobList:<br />**Job A**: <br />\['title': 'Developer'<br />'company': 'Google'<br/>'location': 'San Francisco', 'California'<br />'costOfLiving': 125<br />'yearlySalary': 100000<br />'yearlyBonus': 5000<br />'allowedWeeklyTeleworkDays': 0<br />'retirementBenefits': 0.07<br />'leaveTime': 25<br />'isCurJob': false <br /> 'salaryAdjusted': 80000<br />'bonusAdjusted': 4000 <br />'jobScore': 0 \] <br />**Job B**: <br />['title': 'Developer'<br />'company': 'Amazon'<br/>'location': 'Berlin', 'Germany'<br />'costOfLiving': 125<br />'yearlySalary': 100000<br />'yearlyBonus': 5000<br />'allowedWeeklyTeleworkDays': 5<br />'retirementBenefits': 0.09<br />'leaveTime': 10<br />'isCurJob': false <br /> 'salaryAdjusted': 80000<br />'bonusAdjusted': 4000 <br />'jobScore': 0 | Expect JobA.jobScore =  17458.46<br />Expect JobB.jobScore = 18855.38 | JobA.jobScore=17458.46 <br />JobB.jobScore=18855.38 |Pass |
|36. | Verify that rankList() accepts a list of jobs and correctly returns a sorted list  | 1. Input JobList from test case 35 | Expect sorted list: JobA, JobB | JobA, JobB | Pass |

**Additional UI / System Tests:** 

| Test Case | Purpose | Steps  | Expected Result|  Actual Result | Pass/Fail? |
|-----------|-------|-----------------|------------------|----------------|--------------|
|1. | Verify that *Main Menu* contains each of the 4 options | 1. Start app | Expect the following Strings: <br />"View Current Job," "Add Job Offer," "Comparison Settings," "Comparison"| "View Current Job," "Add Job Offer," "Comparison Settings," "Comparison" | Pass |
|2. | Verify that *Comparison* is disabled if no jobs have been entered | Pre-requisite: No jobs entered into system <br />1. From *Main Menu* attempt to select *Comparison* | Expect no navigation | no navigation  | Pass |
|3. | Ensure that "View Current" button navigates to the right UI | 1. Navigate to *Main Menu* <br /> 2. Select "View Current Job" | Expect "Current Job" UI | "Current Job" | Pass |
|4. | Ensure that "Add Job Offer" button navigates to the right UI | 1. Navigate to *Main Menu* <br /> 2. Select "Add Job Offer" | Expect "New Job" UI | "New Job" | Pass |
|5. | Ensure that "Comparison Settings" button navigates to the right UI | 1. Navigate to *Main Menu* <br /> 2. Select "Comparison Settings" | Expect "Comparison Settings" UI | "Comparison Settings" | Pass |
|6. | Ensure that "Comparison" button navigates to the right UI | Pre-requisite: At least one job offer saved<br />1. Navigate to *Main Menu* <br /> 2. Select "Comparison" | Expect "Job List" UI | "Job List" | Pass |
|7. | Verify that *View Current Job* save button navigates back to *Main Menu* | 1. Navigate to *View Current Job* screen, <br />2. Type in job details and click save | Expect return to *Main Menu* screen | Returned to main menu | Pass |
|8. | Verify that *View Current Job* cancel button navigates back to *Main Menu* | 1. Navigate to *Current Job* screen, <br />2. Click cancel | Expect return to *Main Menu* screen | Returned to main menu | Pass |
|9. | Verify that *View Current Job* screen has a form that populates with the current job fields if it exists; otherwise it is a blank form | Pre-requisite: No current job saved <br /> 1. Navigate from *Main Menu* to *View Current Job*, <br /> 2. Enter current job and save <br /> 3. select "Current Job" job option| Expect form filled with fields that match saved entry | Form fields matched | Pass |
|10. | Check that *View Current Job* edit functionality works and changes overwrite the current information | 1. Add current job,<br /> 2. save, <br /> 3. return to current job screen, edit details and save | Expect updated details | Fields return updated | Pass |
|11. | Verify that *Job Offer* save button clears all fields and does not navigate from screen| 1. Navigate to *Job Offer*,<br />2. enter details, <br />3. click save | Expect blank form on *Job Offer* screen | (Manual test) shows blank form | Pass |
|12. | Verify that *Job Offer* save button allows another Job to be saved| 1. Navigate to *Job Offer*, <br /> 2. enter details, <br />3. click save, <br />4. repeat | Expect form to clear and that db contains correct details for both new entries | (Manual test) details are saved correctly | Pass |
|13. | Verify that *Job Offer* compare button is disabled when there is no current job| Pre-requisite: There is no existing current job. <br />1. Navigate to *Job Offer*, <br /> 2. try to click compare. | Expect no response | (Manual test) Button is disabled | Pass |
|14. | Verify that *Job Offer* compare button is disabled when the user has not entered a new offer| Pre-requisite: There is an existing current job but no offer has been submitted <br /> 1. Navigate to *Job Offer*, <br /> 2. try to click compare.  | Expect no response | (Manual test) Button is disabled | Pass |
|15. | Verify that *Comparison* screen contains sorted list with current clearly indicated| Pre-requisite: There is an existing current job and job offers <br /> 1. Navigate to *Comparison*  | Expect sorted list with current indicated | (Manual test) Job list correctly sorted with current job indicated | Pass |
|16. | Verify that *Comparison* job selection functionality submits correct jobs to table| Pre-requisite: There is an existing current job and at least 1 job offer <br /> 1. Navigate to *Comparison*, <br /> 2. Select two jobs  | Expect table with correct job details for both | (Manual test) Details correct | Pass |
|17. | Verify that *Comparison* allows the selection of only two jobs| Pre-requisite: There are at least three jobs saved <br /> 1. Navigate to *Comparison*, <br /> 2. Select 2 jobs, <br /> 3. Attempt to select one more  | Expect toast | (Manual test) Toast appears | Pass |
|18. | Verify that *Comparison* compare button is disabled when the user has selected less than 2 jobs| Pre-requisite: There are at least 2 existing jobs <br /> 1. Navigate to *Comparison*, <br /> 2. Select no jobs  | Expect compare to be disabled | (Manual test) disabled | Pass |