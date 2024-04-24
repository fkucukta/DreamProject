C:\github\application-development\dream-project\DreamProject.py 
class TaskManager:
    def __init__(self):
        self.tasks = []

    def add_task(self, task):
        self.tasks.append(task)
        print(f"Task added: {task}")

    def view_tasks(self):
        if not self.tasks:
            print("No tasks found.")
        else:
            for i, task in enumerate(self.tasks, start=1):
                print(f"{i}. {task}")

    def delete_task(self, task_number):
        if task_number - 1 < len(self.tasks):
            removed_task = self.tasks.pop(task_number - 1)
            print(f"Task removed: {removed_task}")
        else:
            print("Invalid task number.")
class ReminderManager:
    def __init__(self):
        self.reminders = []

    def add_reminder(self, reminder):
        self.reminders.append(reminder)
        print(f"Reminder added: {reminder}")

    def view_reminders(self):
        if not self.reminders:
            print("No reminders found.")
        else:
            for reminder in self.reminders:
                print(reminder)
def main():
    task_manager = TaskManager()
    reminder_manager = ReminderManager()

    while True:
        print("\nSimple Life Organizer Main Menu")
        print("1. Add Task")
        print("2. View Tasks")
        print("3. Delete Task")
        print("4. Add Reminder")
        print("5. View Reminders")
        print("6. Exit")

        choice = input("Enter your choice: ")

        if choice == "1":
            task = input("Enter the task: ")
            task_manager.add_task(task)
        elif choice == "2":
            task_manager.view_tasks()
        elif choice == "3":
            task_number = int(input("Enter task number to delete: "))
            task_manager.delete_task(task_number)
        elif choice == "4":
            reminder = input("Enter the reminder: ")
            reminder_manager.add_reminder(reminder)
        elif choice == "5":
            reminder_manager.view_reminders()
        elif choice == "6":
            print("Exiting Simple Life Organizer...")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
