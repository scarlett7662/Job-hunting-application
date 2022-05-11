# Design Discussion
## Individual Designs
### jmurphy322
![jmurphy322 design.pdf](./../Design-Individual/jmurphy322/design.pdf)  
Jon
- Cons
	- lacks GUI functionality definitions as either classes or operations
	- lacks jobList attributes. should include "/salaryAdjusted" and "/bonusAdjusted" like msmith's design
	- lacks jobTable attributes. 
	- WeightSettings class should be changed to be more specific. ComparisonSettings is better.

Sijia/Scarlett
- Pros
	- Clear and concise statement of each class. 
	- All requirements has been answered.
- Cons
        - Not sure if this design be lack of driving class.
	- Some attribute may be designed with wrong data type(eg.telework should be Integer from 0-5) 
	- It will be better to add a relationship statement to explain the relationship line.
     
Mallorie
- Pros
	- Think the simple design is a good way to go.
	- I also think your choices of classes makes a lot of sense. It is very clearly laid out.
- Cons
	- Missing a way to distinguish between current job and job offer; maybe a boolean in Job class?
	- Agree with Scarlett that some attributes may need different types

hyang87
- Pros
	-It is a very concise design
	-it adds variable type to attributes 
-Cons
	-score class is kind of useless
	-lacks current job entity
### msmith635
![msmith635 design.pdf](./../Design-Individual/msmith635/design.pdf)  
Jon
- Cons  
	- should calculatescore use job instead of joblist since joblist doesn't include all values required for the calculation?
	- lacks the comparison table between two selected jobs
	- job class, jobscore attribute should be calculated value "/jobScore"
	- i think the user operations could move to other classes and user removed. my understanding is the classes depict data objects and not functionality. a different UML diagram would depict the functionality. i'm not that confident in this though.

Sijia/Scarlett
- Pros
	- Reasonalbe structure of design.
	- Clear statement about relationships. 
- Cons
	-  Not sure what does [0...*] mean in JobList.
	-  I think the Ranking Algorithm could be collected in the JobList, as it doesn't have any attribute and the JobList will be ranked by this algorithm method.

hyang87
- Pros
	- good to have current job and job offer as subclass of job class
	-it adds variable type to attributes 
- Cons
	-User class might be unecessary
	-still needs a comparison table class
### hyang87
![hyang87 design.pdf](./../Design-Individual/hyang87/design.pdf)  
Jon
- Cons  
	- lacks operations for adding and editing jobs/settings
	- lacks jobs list
	- lacks score attribute

Sijia/Scarlett
 - Pros
	-  Clear document layout.
	-  Use Utilities.
- Cons
	-  Lack of datatype for attribute and return type for method
	-  There is no attribute and methods in current job, what make it different with Job offer?
	-  I think the mark with black point is a state diagram mark.

Mallorie
- Pros
	- Nice layout/formatting
	- I think the inclusion of the ComparisonTable class for sorting and handling job comparison is a good idea.
	
- Cons
	- I also wonder if maybe the generalization relationship between CurrentJob and JobOffer could be handled differently; especially as there are no attributes in CurrentJob

### szhao348
![szhao348 design.pdf](./../Design-Individual/szhao348/design.pdf)  
Jon
- Cons  
	- main menu shouldn't display a list. it's only to select from the various GUI options
	- i think the mainmenu operations could move to other classes and mainmenu changed to jobList. my understanding is the classes depict data objects and not functionality. a different UML diagram would depict the functionality. i'm not that confident in this though.
	- plus/minus are meant to show public/private data visibility. everything is marked public.
	- lacks a scoring operating. 

Mallorie
- pros
	- Clear design
	- Lots of attention to detail; I think including visibility (+ or -) may be good for our group design
	- I think its a good idea to use the Job class with the "isCurJob" boolean to distinguish between current and job offer
- cons
	- I agree that MainMenu Class could be changed to JobList class. And then "enterNewJob()", "adjustSettings()", etc could be moved to other classes.
	- I think our design did not need any GUI specific classes or functionality. Would navigation methods fall under that category? Like exit(), or toMainMenu()? (I reread the instructions - we were not required to include GUI specific classes, but I suppose we still can)

hyang87
- pros
	-good inclusion of isCurJob attribute in job class
	-good setup with Comparison Setting class.
- cons
	-some operation could be implemented in UI design such as toMainMenu() method
	- plus is unessary since there is no minus sign
## Team Design
![team design.pdf](./design.pdf)
- Similarities:  
	- Job class and attributes
	- Comparison settings class and attributes

- Differences: 
	- GUI classes and operations
	- The level of detail in terms of attribute and return types as well as visibility information
	- The entry points for each design  
	- Sijia/Scarlett: We use different ways to deal with the ranking method. We need to unify what should be designed attribute and what should be designed as class.

- Justification for design decision:
	- We took concepts from each of the designs and stuck to a simple class structure. 
	- Rather than create subclasses for the current job and job offer, we used a boolean in the Job class to distinguish between the two since these contain all the same details.
	- We also made the decision to keep a JobList class and use the calculateScore() method to calculate all scores at once for the job ranking. This way, the calculation captures the latest Comparison Settings (weights), and we do not have to recalculate scores each time the settings are adjusted.
	- Since both the "enter job offers" menu item (allows you to compare the offer - if its saved - with the current job if it is present) and the "Compare Job Offers" menu item both require a comparison of two jobs, we associated the Job and JobList classes with the ComparisonTable class.
## Summary
Each of the designs had some similarities and also clear differences. By starting with discussion the differences, we were able to weigh the pros and cons of different alternatives and opt for the most practical solution. Scarlett shared her LucidChart with the team so that we could simultaneously make edits. This was very helpful toward clarifying ideas and moving forward with the design. 
