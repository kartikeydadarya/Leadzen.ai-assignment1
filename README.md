# Leadzen.ai-assignment1
# To-do list application 
class TodoList:
    def __init__(self):
        self.tasks = []

    def add_task(self, task):
        self.tasks.append(task)
        print("Task added:", task)

    def delete_task(self, task):
        if task in self.tasks:
            self.tasks.remove(task)
            print("Task deleted:", task)
        else:
            print("Task not found.")

    def mark_completed(self, task):
        if task in self.tasks:
            print("Task marked as completed:", task)
            self.tasks.remove(task)
            self.tasks.append(task + " (Completed)")
        else:
            print("Task not found.")

    def display_tasks(self):
        print("Tasks:")
        for task in self.tasks:
            print("-", task)


def main():
    todo_list = TodoList()

    while True:
        print("\n1. Add task\n2. Delete task\n3. Mark task as completed\n4. Display tasks\n5. Exit")
        choice = input("Enter your choice: ")

        if choice == '1':
            task = input("Enter task: ")
            todo_list.add_task(task)
        elif choice == '2':
            task = input("Enter task to delete: ")
            todo_list.delete_task(task)
        elif choice == '3':
            task = input("Enter task to mark as completed: ")
            todo_list.mark_completed(task)
        elif choice == '4':
            todo_list.display_tasks()
        elif choice == '5':
            print("Exiting...")
            break
        else:
            print("Invalid choice. Please try again.")


if __name__ == "__main__":
    main()
