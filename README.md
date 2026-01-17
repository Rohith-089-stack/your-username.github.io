

attendance = {}   

def add_student(name):
    if name not in attendance:
        attendance[name] = 0
        print(f"{name} added successfully.")
    else:
        print(f"{name} already exists.")

def mark_attendance():
    present_today = []
    print("\nMark Attendance (P/A):")

    for student in attendance:
        status = input(f"{student} (P/A): ").upper()
        if status == 'P':
            attendance[student] += 1
            present_today.append(student)

    print("\nPresent Today:", present_today)

def display_attendance():
    print("\nAttendance Record:")
    for student, count in attendance.items():
        print(f"{student} : {count} days present")
while True:
    print("\n--- Attendance Tracker ---")
    print("1. Add Student")
    print("2. Mark Attendance")
    print("3. View Attendance")
    print("4. Exit")

    choice = input("Enter choice: ")

    if choice == '1':
        name = input("Enter student name: ")
        add_student(name)

    elif choice == '2':
        if len(attendance) == 0:
            print("No students found!")
        else:
            mark_attendance()

    elif choice == '3':
        display_attendance()

    elif choice == '4':
        print("Exiting program.")
        break

    else:
        print("Invalid choice!")
        
