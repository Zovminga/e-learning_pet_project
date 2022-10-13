## Project Overview

The project task is to analyze data on completed courses and subjects of the training e-learning program and answer the following questions (the easiest/hardest courses, RFM analysis etc.)

## Questions to answer

1. How many students have successfully passed only one course? (Successful passing is a credit for the course on the exam).

2. Find the hardest and easiest exam - the courses and exams within the course that have the lowest and highest completion ratios\*.

3. Determine the average term for passing exams for each subject (passing means the last successful passing of the exam by a student).

4. Identify the most popular courses (TOP-3) by the number of registrations for them and top-3 courses with the largest outflow.

5. Find the semester with the lowest course completion ratio and the longest average course completion time between the beginning of 2013 and the end of 2014.

6. Conduct an RFM analysis of students to qualitatively assess your audience.

*\*completion rate = number of successful exams / number of all attempts to pass the exam*

## Datasets:

1. assessments.csv - Dataset contains information about the assessments in the test. Typically, each subject in a semester includes a series of graded tests, followed by a final examination test (exam).

	code\_module - subject id.

	code\_presentation - semester (ID).

	id\_assessment - test (assessment ID).

	assessment\_type - type of test. There are three types of assessment: teacher assessment (TMA), computer-aided assessment (CMA), and course exam (Exam).

	date - information about the final date (deadline) of passing the test. Calculated as the number of days since the beginning of the semester. The start date of the semester is numbered 0 (zero).

	weight -  weight of the test in % in the assessment for the course. Usually exams are considered separately and have a weight of 100%; the sum of all other scores is 100%.

2. courses.csv - Dataset contains a list of subjects by semester.

	code\_module - subject id.

	code\_presentation - semester (ID).

	module\_presentation\_length - duration of the semester in days.

3. studentAssessment.csv - Dataset contains student test scores. If a student does not submit work for assessment, the result is not recorded in the spreadsheet.

	id\_assessment - test (assessment ID).

	id\_student - student identification number (ID).

	date\_submitted - The date the student passed the test, measured as the number of days since the beginning of the semester.

	is\_banked - the fact that the test was re-credited from the previous semester (sometimes courses are credited to students who have returned from academic leave).

	score - the student's score on this test. The range is from 0 to 100. A score below 40 fails the test.

4. studentRegistration.csv - Dataset contains information about the date the student registered for the course in the semester.

	code\_module - subject id.

	code\_presentation - semester (ID).

	id\_student - student identification number (ID).

	date\_registration - student subject registration date. This is the number of days measured from the start of the semester (for example, a negative value of -30 means that the student registered for the course 30 days before the start of the course).

	date\_unregistration - the date the student was unregistered from the subject. For students who have completed the course, this field is left blank.

## Conclusions

Courses with the shortest deadlines and the shortest duration have the lowest completion ratios. An example - subject **DDD** in semester **2013B**.
Courses with short deadlines and high churn ratios have difficult final exams. **Top 3** courses with high churn rates - **CCC-2014J**, **DDD-2013B**, **CCC-2014B**.
Most students have an average time of passing exams with the first attempt and the highest score. As a result, the e-learning program shows **positive results** and **students cope with it**.