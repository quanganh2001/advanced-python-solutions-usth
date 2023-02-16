# Practical work 1: Student mark management
## Functions
- Input functions:
    + Input number of students in a class
    + Input student information: id, name, date of birth
    + Input number of courses
    + Input course information: id, name
    + Select a course, input marks for student in this course
```py
# Define a dictionary to store student information
students = {}

# Define a dictionary to store course information
courses = {}

# Define a dictionary to store marks
marks = {}

# Define function to input student information
def input_students():
    num_students = int(input("Enter the number of students in the class: "))
    for i in range(num_students):
        student_id = input("Enter the student ID: ")
        student_name = input("Enter the student name: ")
        student_dob = input("Enter the student date of birth: ")
        students[student_id] = {"name": student_name, "dob": student_dob}

# Define function to input course information
def input_courses():
    num_courses = int(input("Enter the number of courses: "))
    for i in range(num_courses):
        course_id = input("Enter the course ID: ")
        course_name = input("Enter the course name: ")
        courses[course_id] = {"name": course_name}

# Define function to select a course and input marks for students
def input_marks():
    course_id = input("Enter the course ID: ")
    if course_id not in courses:
        print("Invalid course ID")
        return
    for student_id in students:
        mark = float(input(f"Enter the mark for {students[student_id]['name']}: "))
        if student_id not in marks:
            marks[student_id] = {}
        marks[student_id][course_id] = mark

# Define function to list courses
def list_courses():
    for course_id in courses:
        print(f"{course_id}: {courses[course_id]['name']}")

# Define function to list students
def list_students():
    for student_id in students:
        print(f"{student_id}: {students[student_id]['name']}")

# Define function to show marks for a given course
def show_marks():
    course_id = input("Enter the course ID: ")
    if course_id not in courses:
        print("Invalid course ID")
        return
    for student_id in students:
        if student_id in marks and course_id in marks[student_id]:
            print(f"{students[student_id]['name']}: {marks[student_id][course_id]}")
        else:
            print(f"{students[student_id]['name']}: N/A")
```
## Listing functions:
- List courses
- List students
- Show student marks for a given course
```py
# Main program
input_students()
input_courses()

while True:
    print("Select an option")
    print("1. Input marks for a course")
    print("2. List courses")
    print("3. List students")
    print("4. Show student marks for a given choice")
    print("5. Quit")
    choice = input("Enter your choice: ")
    if choice == "1":
        input_marks()
    elif choice == "2":
        list_courses()
    elif choice == "3":
        list_students()
    elif choice == "4":
        show_marks()
    elif choice == "5":
        break
    else:
        print("Invalid choice!")
```
Output:
```txt
Enter the number of students in the class: 2
Enter the student ID: BA10-002
Enter the student name: Quang Anh
Enter the student date of birth: 27 October 2001
Enter the student ID: BA10-045
Enter the student name: Hiep
Enter the student date of birth: 12 May 2001
Enter the number of courses: 2
Enter the course ID: FR2
Enter the course name: ADS
Enter the course ID: Algorithm
Enter the course name: Algorithm
Select an option
1. Input marks for a course
2. List courses
3. List students
4. Show student marks for a given choice
5. Quit
Enter your choice: 1
Enter the course ID: FR2
Enter the mark for Quang Anh: 16
Enter the mark for Hiep: 11
Select an option
1. Input marks for a course
2. List courses
3. List students
4. Show student marks for a given choice
5. Quit
Enter your choice: 1
Enter the course ID: Algorithm
Enter the mark for Quang Anh: 12.5
Enter the mark for Hiep: 8.5
Select an option
1. Input marks for a course
2. List courses
3. List students
4. Show student marks for a given choice
5. Quit
Enter your choice: 2
FR2: ADS
Algorithm: Algorithm
Select an option
1. Input marks for a course
2. List courses
3. List students
4. Show student marks for a given choice
5. Quit
Enter your choice: 3
BA10-002: Quang Anh
BA10-045: Hiep
Select an option
1. Input marks for a course
2. List courses
3. List students
4. Show student marks for a given choice
5. Quit
Enter your choice: 4
Enter the course ID: FR2
Quang Anh: 16.0
Hiep: 11.0
Select an option
1. Input marks for a course
2. List courses
4. Show student marks for a given choice
5. Quit
Enter your choice: 4
Enter the course ID: Algorithm
Quang Anh: 12.5
Hiep: 8.5
Select an option
1. Input marks for a course
2. List courses
3. List students
4. Show student marks for a given choice
5. Quit
Enter your choice: 5
```
Your can check source code in Kaggle: https://www.kaggle.com/code/quanganh2001/practical-work-1-student-mark-management
