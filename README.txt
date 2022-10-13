## Questions to answer
The project task is to analyze data on completed courses and subjects of the training program and answer the following questions:

1. How many students have successfully passed only one course? (Successful passing is a credit for the course on the exam).

2. Find the hardest and easiest exam - the courses and exams within the course that have the lowest and highest completion ratios*.

3. Determine the average term for passing exams for each subject (passing means the last successful passing of the exam by a student).

4. Identify the most popular courses (TOP-3) by the number of registrations for them and top-3 courses with the largest outflow.

5. Find the semester with the lowest course completion ratio and the longest average course completion time between the beginning of 2013 and the end of 2014.

6. Conduct an RFM analysis of students to qualitatively assess your audience.

**completion rate = number of successful exams / number of all attempts to pass the exam*

## Datasets:

1. assessments.csv - Dataset contains information about the assessments in the test. Typically, each subject in a semester includes a series of graded tests, followed by a final examination test (exam).

	code_module - subject id.

	code_presentation - semester (ID).

	id_assessment - test (assessment ID).

	assessment_type - type of test. There are three types of assessment: teacher assessment (TMA), computer-aided assessment (CMA), and course exam (Exam).

	date - information about the final date (deadline) of passing the test. Calculated as the number of days since the beginning of the semester. The start date of the semester is numbered 0 (zero).

	weight — weight of the test in % in the assessment for the course. Usually exams are considered separately and have a weight of 100%; the sum of all other scores is 100%.

2. courses.csv - Dataset contains a list of subjects by semester.

	code_module - subject id.

	code_presentation - semester (ID).

	module_presentation_length - duration of the semester in days.

3. studentAssessment.csv - Dataset contains student test scores. If a student does not submit work for assessment, the result is not recorded in the spreadsheet.

	id_assessment - test (assessment ID).

	id_student - student identification number (ID).

	date_submitted - The date the student passed the test, measured as the number of days since the beginning of the semester.

	is_banked - the fact that the test was re-credited from the previous semester (sometimes courses are credited to students who have returned from academic leave).

	score - the student's score on this test. The range is from 0 to 100. A score below 40 fails the test.

4. studentRegistration.csv - Dataset contains information about the date the student registered for the course in the semester.
	
	code_module - subject id.

	code_presentation - semester (ID).

	id_student - student identification number (ID).

	date_registration - student subject registration date. This is the number of days measured from the start of the semester (for example, a negative value of -30 means that the student registered for the course 30 days before the start of the course).

	date_unregistration - the date the student was unregistered from the subject. For students who have completed the course, this field is left blank.