# GradeBook Analyzer CLI

> Command-line gradebook assistant for quick mark analysis and reporting.

## 📚 Project Overview
The script helps lecturers enter or import student marks, run core statistics, assign letter grades, and export a tidy report.

## ✨ Features
- **Two data entry modes** – type marks manually or import from a `.csv` file.
- **Class statistics** – average, median, highest score (with student), and lowest score (with student).
- **Automatic grading** – assigns letter grades (A–F) based on score thresholds.
- **Grade distribution** – counts how many students earned each letter grade.
- **Pass / fail filter** – list comprehension separates students using a configurable pass mark (default 40).
- **Tabbed summary table** – prints every student with marks and grade in a clean, tab-separated layout.
- **Optional CSV export** – save the generated report to a new file directly from the CLI.

## 🗂️ Repository Structure
```
gradebook_analyser/
├── gradebook.py
├── students.csv        # example input (optional)
└── final_report.csv    # created when you export results (optional)
```

## 🚀 Setup & Usage
1. **Download** or clone this repository.
2. **Open a terminal** in the project folder:
   ```bash
   cd gradebook_analyser
   ```
3. **Run the program**:
   ```bash
   python gradebook.py
   ```
4. **Follow the on-screen menu** to choose:
   - `1` – **Manual Entry**: enter student names and marks interactively.
   - `2` – **CSV Import**: load marks from a CSV file in the same folder.
   - `Q` – Quit the application.

### CSV Format Guide
If you import data, make sure your file looks like this (no headers required but supported):
```csv
Name,Mark
Rohan Kumar,88
Priya Sharma,92
Amit Patel,58
```
Marks outside 0–100 or non-numeric values are skipped with a warning so you can fix them later.

## 🧪 Sample Runs
### 1. Manual Entry (5 Students)
```
-----------------------------------------
GradeBook Analyser by Prabhat Bhatia

How would you like to load data?
1. Manual Entry (Type names and marks one by one)
2. CSV Import (Load a .csv file)
Q. Quit
-----------------------------------------
Your choice (1, 2, or Q): 1

=> Manual Data Entry 

Enter student name and marks (0-100).

Enter student name: Alice
Enter Alice's mark (0-100): 
95
-> Added Alice with 95 marks.

Do you want to enter more names? [Y/N]: y
Enter student name: Bob
Enter Bob's mark (0-100): 
82
-> Added Bob with 82 marks.

Do you want to enter more names? [Y/N]: y
Enter student name: Charlie
Enter Charlie's mark (0-100): 
78
-> Added Charlie with 78 marks.

Do you want to enter more names? [Y/N]: y
Enter student name: David
Enter David's mark (0-100): 
55
-> Added David with 55 marks.

Do you want to enter more names? [Y/N]: y
Enter student name: Emily
Enter Emily's mark (0-100): 
32
-> Added Emily with 32 marks.

Do you want to enter more names? [Y/N]: n

Manual entry complete. 5 students recorded.

-- Class Statistics --
Total Students:   5
Average Score:    68.4
Median Score:     78
Highest Score:    95 (by Alice)
Lowest Score:     32 (by Emily)
Letter grades have been assigned.

-- Grade Distribution --
Grade A: 1 student(s)
Grade B: 1 student(s)
Grade C: 1 student(s)
Grade D: 1 student(s)
Grade F: 1 student(s)

-- Pass/Fail Analysis (Passing = 40) --
Total Passed: 4
Students: Alice, Bob, Charlie, David

Total Failed: 1
Students: Emily

-- Full Student Report --
Name	Marks	Grade
--------------------------
Alice	95	A
Bob	82	B
Charlie	78	C
David	55	D
Emily	32	F
--------------------------

Would you like to export this full report to a CSV file? (y/n): n
Skipping export

========================================
Do you want to repeat the process? (y/n): n

Ending code.
```

### 2. CSV Import (students.csv)
**Sample file:**
```csv
Name,Mark
Rohan Kumar,88
Priya Sharma,92
Amit Patel,58
Sneha Reddy,72
Vihan Singh,35
Ananya Joshi,99
Aditya Rao,79
Dev Mehra,60
Isha Verma,81
Kabir Gupta,40
```

**Program output:**
```
-----------------------------------------
GradeBook Analyser by Prabhat Bhatia

How would you like to load data?
1. Manual Entry (Type names and marks one by one)
2. CSV Import (Load a .csv file)
Q. Quit
-----------------------------------------
Your choice (1, 2, or Q): 2

=>CSV Data Import
Enter the name of the csv file: students.csv

CSV import complete. 10 students loaded from 'students.csv'.

-- Class Statistics --
Total Students:   10
Average Score:    70.4
Median Score:     75.5
Highest Score:    99 (by Ananya Joshi)
Lowest Score:     35 (by Vihan Singh)
Letter grades have been assigned.

-- Grade Distribution --
Grade A: 2 student(s)
Grade B: 2 student(s)
Grade C: 2 student(s)
Grade D: 2 student(s)
Grade F: 2 student(s)

-- Pass/Fail Analysis (Passing = 40) --
Total Passed: 9
Students: Rohan Kumar, Priya Sharma, Amit Patel, Sneha Reddy, Ananya Joshi, Aditya Rao, Dev Mehra, Isha Verma, Kabir Gupta

Total Failed: 1
Students: Vihan Singh

-- Full Student Report --
Name	Marks	Grade
--------------------------
Aditya Rao	79	C
Amit Patel	58	D
Ananya Joshi	99	A
Dev Mehra	60	D
Isha Verma	81	B
Kabir Gupta	40	F
Priya Sharma	92	A
Rohan Kumar	88	B
Sneha Reddy	72	C
Vihan Singh	35	F
--------------------------

Would you like to export this full report to a CSV file? (y/n): y
Enter a name for your export file: final_report.csv

Success! Report exported to 'final_report.csv'

========================================
Do you want to repeat the process? (y/n): n

Ending code.
```

## 👤 Author & Course
- Prabhat Bhatia
- 2501410006
- B.Tech CSE Cyber Security(First Semester)
- 6th October 2025
- Programming With Python - Lab Assignment 2
