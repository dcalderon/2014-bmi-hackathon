# 2014 BMI Hackathon
This dashboard is part of BMI's 2014 hackathon hosted in Monterrey. Part 1 of the challenge involved creating classifiers that could predict aspects of a patient's AML treatment such as likelihood of remission, remission duration, and overall survival. The prompt we were using for this portion of the hackathon is copied from Katie Planey's emails (with slight modifications) as follows:

### Software Design
Translating model results to patient and doctor Hackathon members that wish to focus more on software implementation will work to address aspects of engaging the actual patient with the research results from above.  They will create “dummy” results so that they can progress while students are still working on the predicting results from part I. 

##### We will focus on
determining the most relevant types of information to present to patients. This challenge, like most supervised clinical oncology informatics methods, predict survival and/or relapse. This can lead to functional insight and new ground-breaking therapies, but what’s important to give to current patients? Would you present simply their change of survival? Would you try and explain your entire model to them? What about visualizations? Is a report for the patient’s clinical preferable? These questions align with other challenges proposed by the NML competition.

##### Other challenges to be addressed if there’s time
Effectively presenting the information to patients in ways that understandable to them (i.e. visualization techniques); Improving the communication mechanisms between patients and their providers Designing features that “empower” the patient Designing new ways to incorporate patient-generated data into clinical decision-making Note that part II doesn’t require a working GUI - perhaps a script that pulls out model results and creates a succinct 1-page printout for the patient, and a 1-page print-out for the doctor, is a good first step.

## File structure

LICENSE - Open source license

README.md - Typical readme file.

report.html - The report html file. It pulls from the style.css and tests.js.

style.css - Standard style sheet.

tests.js - Javascript file with chart javascript for the tests.

demo.html - Self-contained demo file. Basically the report.html file with the javascript and style sheets included.

## Design Decisions

As stated in the prompt we did not want to clutter the report with unecessary information. The idea was to focus on the tests that conveyed the most relevant information.

![alt tag](https://raw.githubusercontent.com/dcalderon/2014-bmi-hackathon/master/Screenshot.png)

At the top of the report we have the patient's name, diagnosis, and next appointment, which quickly provides general context for what we are looking at.

Below this title we have the main table with most of the information. In the top row from left to right we have a day count since diagnosis, the main details of the model and a link to a support group for AML (currently with a placeholder url) and a link to some recent literature on AML. On hover the bold details of the model provide a tooltip with model prediction confidence information attempting to add some background to classification claims.

In the middle of the page we have a graphical representation of three different tests. These are also placeholders, but you can imagine them containing the most relevant information to keep track of AML progression. Like the model text above, when the cursor hovers over a data point more detailed information is displayed. Under each graph there is a button that gives the clinician the option of sharing the test with the patient, and we were careful to include a second confirmation to insure no accidental button presses.

The color scheme of the display was chosen to provide a soothing background that doesn't confuse the interpretation of any of the info displays.

While we only built a display for a clinician we had in mind the process of the physician building a relationship with their patient. Our sharing button mechanism was included as a way of empowering the patient with the ability to learn details about their AML care by way of requesting access from their doctor. The idea was that when the patient requests information on a test the clinician could share pieces of information they felt was relevant.

In the future it would have been helpful to try and generalize this pattern for other chronic diseases and generalize the number of tests displayed. We would also like to have implemented a rudimentary permissions system for sharing test information. Another step would be to build an aggregate dashboard for a doctor who has many patients with different diagnosises. Looking at this dashboard the doctor could keep track of general trends in their patient's health.

## Technologies used
We browsed many dashboards from various professions for inspiration. In particular I appreciated the simplicity of [this one](https://dribbble.com/shots/780188-Morning/attachments/78031).

Data visualizations online can sometimes be especially tricky, however I found [Chart.js](http://www.chartjs.org/) to be an awesome solution for our needs. Out of the box the 6 graph types were beautiful, responsive, and easy to understand.

For the tooltips I borrowed code from [this](http://cbracco.me/a-simple-css-tooltip/) website.

The confirmation button was based on code from [this](http://www.sanwebe.com/2013/01/40-css-buttons-from-codepen) blog post.

## Demo
To see a live demo of this dashboard simply download the demo.html and double click on the file in your downloads folder. It is totally self-contained (has the css and javascript code in the html file, which is not standard procedure) and should open automatically in your preferred browser.