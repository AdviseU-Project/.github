# AdviseU - Data Needed

AdviseU is a web application designed to assist students and advisors at Oregon State University (OSU) in generating optimal course plans. To ensure the application functions effectively, the following data is required:

## 1. **Course Data**
Comprehensive information about all available courses at OSU:
- **Course ID**: A unique identifier for each course (e.g., CS101).
- **Course Title**: The full name of the course.
- **Department**: The department or college offering the course.
- **Course Description**: A summary of the course content.
- **Credits**: The number of credits the course offers.
- **Prerequisites**: Courses or knowledge required before enrolling.
- **Corequisites**: Courses that must be taken simultaneously, if applicable.
- **Difficulty Level**: An indicator of course difficulty (could be based on historical data or subjective assessment).
- **Required for Degree**: Information on whether the course is required for specific degrees or majors.
- **Elective Options**: Classification if the course can be used as an elective within a program.

## 2. **Course Scheduling**
Data on when courses are available throughout the academic year:
- **Terms Offered**: Fall, Winter, Spring, Summer, or specific years.
- **Availability**: Whether the course is currently available or if it's canceled/postponed.
- **Class Time/Location**: Time, day, and location of each class, if available.
- **Instructor Information**: Name and department of the course instructor.

## 3. **Degree Requirements**
Information specific to degree programs that the application will use to automatically include required courses:
- **Degree Program**: Name and details of the degree (e.g., Computer Science, Mechanical Engineering).
- **Degree Option**: Name and details of the degree option (e.g., Computer Systems, Data Science).
- **Required Courses**: A list of all courses required to complete the degree.
- **Elective Options**: Options for fulfilling elective requirements.
- **Capstone/Thesis Requirement**: Whether a capstone or thesis is required.

## 4. **Graduation Timeline**
Data that helps students plan for graduation:
- **Expected Graduation Date**: The student's projected graduation date.
- **Course Load Constraints**: Limits on the number of courses or credits a student can take per term.

## 5. **Student Preferences**
Personalized preferences to create custom course schedules:
- **Preferred Course Load**: Number of courses or credits a student prefers per term.
- **Interest Areas**: Areas of interest that can influence elective recommendations.
- **Course Timing Preferences**: Preferences for morning, afternoon, or evening classes.
- **Balance of Difficulty**: A balance between easy and challenging courses.

## 6. **Historical Data (Optional)**
Historical information that could help refine scheduling and recommendations:
- **Previous Enrollment Trends**: How many students typically enroll in each course.
- **Course Success Rates**: Average grades or success rates to assess difficulty.
- **Waitlist Data**: Information on how likely it is for students to get into a course.

## 7. **Integration with OSU Systems**
To ensure the tool functions in real time:
- **Registrar Data Access**: Ability to pull live course data from OSU’s registrar system.
- **MyDegrees Data**: Access to the student's current progress on their degree plan.
- **Real-Time Enrollment Data**: Live data on current course enrollments to help with availability and waitlist predictions.

---

## Data Sources
- **OSU Course Catalog**: For retrieving course information.
- **OSU Registrar**: For real-time scheduling, availability, and enrollment data.
- **MyDegrees**: For degree progress tracking and existing course plans.
- **[OSU Developer Portal APIs](https://developer.oregonstate.edu/apis)**
  - [Academic Disciplines v1](https://developer.oregonstate.edu/api/8)
  - [Terms v1](https://developer.oregonstate.edu/api/17)
---

This data will allow AdviseU to provide a personalized and up-to-date course planning experience for students and advisors at OSU.
