## Disclaimer
For privacy reasons, I cannot show the code. However, I will give a brief overview of how it works below.

## About this Project
This application is built with JavaScript and Node.js and uses the Excel.js and Moment.js libraries for styling. It is used to help the computer science department schedule their courses at the beginning of a semester, and it has been adapted to work with data from the math department too. It runs on the command line, and it outputs a styled Excel sheet given an input Excel sheet that contains course data for a specific semester.

## Example Input
![Input Sheet Example](https://user-images.githubusercontent.com/60369962/226731189-efbf6cd1-7066-4761-8ab7-345a0610ce4b.JPG)

## Example Output
![Output Schedule Example](https://user-images.githubusercontent.com/60369962/226731319-fe1876f2-b5fc-476a-83bd-e1f5ef4cbe70.JPG)
![Output Report Tab Example](https://user-images.githubusercontent.com/60369962/226731333-e4c633ca-8e41-44ed-9be5-7edc08e20fff.JPG)

## How it Works
- The user is asked to choose an input .xlsx file, a subject (CS or MATH for example), and a color code (I for instructor and C for course) for the schedule styling.
- The program validates whether the input sheet is properly formatted or not. It returns an error if it is not properly formatted.
- After the input validation, it reads the contents of the input file row by row and stores the data in an object. It only reads from the rows that have the same subject as what the user chose.
- The object that stores the data from the input sheet is processed, and each course is marked by what tabs they go into in the output excel sheet. Courses with scheduling conflicts are also marked.
- An output schedule Excel sheet is generated based on what data is inside the object, and courses go into their assigned tabs. A report tab is also generated for any courses with scheduling conflicts.

## Features
- Given a configuration file, the user can choose which courses to display in specific tabs. The schedule output colors can also be displayed based on instructors or courses.
- Users can schedule extra labs or tutoring sessions that are not currently on the semester schedule.
- The report sheet groups courses with scheduling conflicts into four categories: unscheduled sections, flagged sections, prerequisite conflict sections, and instructor scheduling confict sections.
  - Unscheduled Sections: These courses do not have a set time and are scheduled based on the availability of the student and professor. These usually consist of independent research projects since they are one on one.
  - Flagged Sections: These courses have a conflict since their duration does not meet the requirements for their number of units. Their meeting times could either be too short or too long based on the California State University unit system.
  - Prerequisite Conflict Sections: Two courses that can be taken at the same time cannot have a time overlap since it would make it inconvenient for students to complete their core coursework.
  - Instructor Conflict Sections: An instructor cannot teach more than two courses at the same time.
