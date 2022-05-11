# Use Case Model

*This is the template for your use case model. The parts in italics are concise explanations of what should go in the corresponding sections and should not appear in the final document.*

**Author**: Sijia Zhao, Team 004

## 1 Use Case Diagram

![use case dia](./img/Use%20case%20diagram.png)

## 2 Use Case Descriptions

*For each use case in the use case diagram, this section should contain a description, with the following elements:*

- *Requirements:*
In this use case, we assume the user has verified the identification and has permission to access this system.

- *Pre-conditions:*
The user interface has been built, and the database has been well settled. 

- *Post-conditions*
Any change in the use cases should be saved in the local file.

- *Scenarios:*   
1 The user creates and edits detail for a new job, editable contents include
    - Title
    - Company
    - Location 
    - Cost of living in the location 
    - Yearly salary
    - Yearly bonus
    - Allowed weekly telework days
    - Retirement benefits 
    - Leave time

  1.1 The user saves the updating for job details and then exits the current interface and returns to the main menu.

  1.2 The user saves the updating for job details and then start a new comparison with current job (if current job is saved).

  1.3 The user exits the current interface and returns to the main menu without saving.

2. The user view/edit detail for a current job, editable contents same with above.
  
  2.1 The user saves the updating and then exits the current interface and returns to the main menu.

3. The user starts a job comparison, selects two jobs from the previously-saved and ranked job list, views the comparison table. 

4. The user adjusts the comparison setting, reassigns new weights of yearly salary, bonus, weekly telework days,  retirement benefits, and leave times.
