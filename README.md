# SCHOOL-ADMINISTRATION-USING-PYTHON
class SchoolAdministration:
    def _init_(self):
        self.students = {}

    def add_student(self, name, age, grade):
        if name in self.students:
            print(f"Student {name} is already in the system.")
        else:
            self.students[name] = {"age": age, "grade": grade}
            print(f"Student {name} added successfully.")

    def remove_student(self, name):
        if name in self.students:
            del self.students[name]
            print(f"Student {name} removed successfully.")
        else:
            print(f"Student {name} not found in the system.")

    def view_students(self):
        if not self.students:
            print("No students in the system.")
        else:
            print("Students currently in the system:")
            for name, details in self.students.items():
                age = details["age"]
                grade = details["grade"]
                print(f"Name: {name}, Age: {age}, Grade: {grade}")

def main():
    system = SchoolAdministration()

    while True:
        print("\nSchool Administration System")
        print("1. Add Student")
        print("2. Remove Student")
        print("3. View Students")
        print("4. Exit")

        choice = input("Enter your choice (1-4): ")

        if choice == '1':
            name = input("Enter the student's name: ")
            age = input("Enter the student's age: ")
            grade = input("Enter the student's grade: ")
            system.add_student(name, age, grade)

        elif choice == '2':
            name = input("Enter the student's name to remove: ")
            system.remove_student(name)

        elif choice == '3':
            system.view_students()

        elif choice == '4':
            print("Exiting the system. Goodbye!")
            break

        else:
            print("Invalid choice. Please try again.")

if _name_ == "_main_":
    main()
