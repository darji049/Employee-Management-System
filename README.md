# Employee-Management-System
# Employee Management System (EMS)

# Step 1: Initialize Employee Data
employees = {
    101: {'name': 'Satya', 'age': 27, 'department': 'HR', 'salary': 50000},
    102: {'name': 'Ramesh', 'age': 35, 'department': 'Finance', 'salary': 60000},
}

# Step 2: Define Menu System
def main_menu():
    while True:
        print("\n=== Employee Management System ===")
        print("1. Add Employee")
        print("2. View All Employees")
        print("3. Search for Employee")
        print("4. Exit")
        choice = input("Enter your choice: ")
        
        if choice == '1':
            add_employee()
        elif choice == '2':
            view_employees()
        elif choice == '3':
            search_employee()
        elif choice == '4':
            print("Thank you for using the Employee Management System!")
            break
        else:
            print("Invalid choice. Please try again.")

# Step 3: Add Employee Functionality
def add_employee():
    try:
        emp_id = int(input("Enter Employee ID: "))
        if emp_id in employees:
            print("Employee ID already exists. Please use a unique ID.")
            return
        
        name = input("Enter Employee Name: ")
        age = int(input("Enter Employee Age: "))
        department = input("Enter Employee Department: ")
        salary = float(input("Enter Employee Salary: "))
        
        employees[emp_id] = {'name': name, 'age': age, 'department': department, 'salary': salary}
        print(f"Employee {name} added successfully!")
    except ValueError:
        print("Invalid input. Please enter correct details.")

# Step 4: View All Employees
def view_employees():
    if not employees:
        print("No employees available.")
    else:
        print("\nEmployee Details:")
        print(f"{'ID':<10}{'Name':<20}{'Age':<10}{'Department':<20}{'Salary':<10}")
        print("-" * 70)
        for emp_id, details in employees.items():
            print(f"{emp_id:<10}{details['name']:<20}{details['age']:<10}{details['department']:<20}{details['salary']:<10.2f}")

# Step 5: Search for an Employee by ID
def search_employee():
    try:
        emp_id = int(input("Enter Employee ID to search: "))
        if emp_id in employees:
            details = employees[emp_id]
            print("\nEmployee Found:")
            print(f"Name: {details['name']}")
            print(f"Age: {details['age']}")
            print(f"Department: {details['department']}")
            print(f"Salary: {details['salary']:.2f}")
        else:
            print("Employee not found.")
    except ValueError:
        print("Invalid input. Please enter a numeric Employee ID.")

# Step 6: Exit
if __name__ == "__main__":
    main_menu()
