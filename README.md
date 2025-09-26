# Code Challenge: Student Enrollment Report Generator

## 🎯 Objective
Your goal is to process and consolidate data from three different source files (`users.json`, `courses.xml`, `enrollment.csv`) to produce two final, unified summary reports. This task tests your ability to parse different file formats, merge data from multiple sources, perform data aggregation, and handle data transformation.

---

## 📖 The Scenario
You are a developer on the Student Information Systems team at a university. The registrar's office needs a clean, consolidated report of all students who are **currently enrolled** in courses for the upcoming term. Your system currently stores data in three separate formats, and you need to write a script to bring them all together.

---

## 📂 Input Data Files

You are provided with three files:

1.  **`users.json`**
    * **Format:** JSON
    * **Content:** Contains detailed information for each student, identified by a unique `UserID`. Includes their name, email, and other demographic data.

2.  **`courses.xml`**
    * **Format:** XML
    * **Content:** Contains detailed information for each course, identified by a unique `CourseID`. Includes the course title, description, schedule, and credit hours.

3.  **`enrollments.csv`**
    * **Format:** CSV
    * **Content:** The intersection file that links users to courses. It contains the `UserID`, `CourseID`, and the status of the enrollment action.

---

## 💻 The Task

Write a program, in the language of your choice, that performs the following actions:

1.  **Read and Parse:** Ingest data from the three provided source files.
2.  **Filter:** Identify only the records where the student is actively **enrolled**. The `EnrollmentCode` 'E' signifies an enrolled status. Records with 'W' (Withdrawn) or 'D' (Dropped) should be ignored for the final report.
3.  **Combine and Aggregate:** For each valid enrollment record, combine information from all three files. You will need to look up user details using `UserID` and course details using `CourseID`.
4.  **Generate Output:** Create **two separate CSV files**: `enrollment_summary.csv` and `course_summary.csv`.

### Output File 1: `enrollment_summary.csv`

This file should provide a summary of each student's total enrolled credit hours. Each row represents a unique student.

**Columns:**

| ColumnName | Description | Source |
| :--- | :--- | :--- |
| `UserID` | The unique identifier for the user. | `users.json` |
| `UserFullName` | The user's first and last name combined. | `users.json` |
| `UserEmail` | The user's email address. | `users.json` |
| `UserDateOfBirth` | The user's date of birth. | `users.json` |
| `UserAddress` | The user's full address, concatenated. | `users.json` |
| `TotalCreditHours` | The sum of credit hours for all courses the user is actively enrolled in. | `courses.xml` & `enrollments.csv` |

**Sample Row:**

```csv
UserID,UserFullName,UserEmail,UserDateOfBirth,UserAddress,TotalCreditHours
99999,"Jane Doe","jane.doe@example.edu","1999-05-21","123 Oak St, Springfield, IL, 62704",12
```

### Output File 2: `course_summary.csv`

This file should provide a summary of enrollment counts for each course. Each row represents a unique course.

**Columns:**

| ColumnName | Description | Source |
| :--- | :--- | :--- |
| `CourseID` | The unique identifier for the course. | `courses.xml` |
| `CourseTitle` | The full title of the course. | `courses.xml` |
| `TermCode` | The code for the academic term. | `courses.xml` |
| `EnrolledStudentCount` | The total number of students actively enrolled in the course. | `enrollments.csv` |

**Sample Row:**

```csv
CourseID,CourseTitle,TermCode,EnrolledStudentCount
ABC-101,"Introduction to Fictional Studies","FA2025",88
```

---

## Programming Language and Solution Constraints

You are welcome to approach this how ever you see fit.  How the problem is solved will be considered part of the evaluation. Be creative and use the tools at your disposal.

**Note:** You must be able to completly speak to your solution, and walk the team through how you solved the problem. The team will ask questions about your solution.

---

## 🚀 Submission

Submit your code as a `Pull Request` on GitHub.  Provide your complete source code, along with a brief explanation of how to run your program to generate the output files.

Good luck!
