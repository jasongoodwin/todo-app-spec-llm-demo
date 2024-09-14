# PyToDo: Terminal Todo App Specification

## Overview
PyToDo is a command-line todo application written in Python, designed for Linux/Unix terminals. It uses a CSV file for data persistence and provides a simple interface for managing tasks.

## Features
1. CSV-backed storage
2. Add new todo items
3. Complete existing items
4. Remove items
5. Display open and completed items in separate columns
6. Interact with items using numerical identifiers
7. Track date added and completed for each item

## Data Structure
The CSV file will have the following columns:
- id: Unique identifier for each item
- task: Description of the todo item
- status: "open" or "completed"
- date_added: Date and time when the item was added
- date_completed: Date and time when the item was completed (empty for open items)

## User Interface
The app will display two columns:
1. Open Items
2. Completed Items

Each item will be displayed with its ID, allowing users to interact with specific items.

## Commands
- add: Add a new todo item
- complete <id>: Mark an item as completed
- remove <id>: Remove an item from the list
- quit: Exit the application

## Example Screens

1. Main Screen
```
PyToDo - Your Terminal Todo App

Open Items                 | Completed Items
---------------------------|---------------------------
1. Buy groceries           | 4. Pay electricity bill
2. Finish project report   | 5. Call dentist
3. Schedule team meeting   |

Enter command (add/complete/remove/quit):
```

2. Add Item
```
Enter command (add/complete/remove/quit): add
Enter new todo item: Prepare presentation for Monday
Item added successfully!

Open Items                 | Completed Items
---------------------------|---------------------------
1. Buy groceries           | 4. Pay electricity bill
2. Finish project report   | 5. Call dentist
3. Schedule team meeting   |
6. Prepare presentation    |
   for Monday              |

Enter command (add/complete/remove/quit):
```

3. Complete Item
```
Enter command (add/complete/remove/quit): complete 2
Marked item 2 as completed!

Open Items                 | Completed Items
---------------------------|---------------------------
1. Buy groceries           | 2. Finish project report
3. Schedule team meeting   | 4. Pay electricity bill
6. Prepare presentation    | 5. Call dentist
   for Monday              |

Enter command (add/complete/remove/quit):
```

4. Remove Item
```
Enter command (add/complete/remove/quit): remove 5
Removed item 5 from the list!

Open Items                 | Completed Items
---------------------------|---------------------------
1. Buy groceries           | 2. Finish project report
3. Schedule team meeting   | 4. Pay electricity bill
6. Prepare presentation    |
   for Monday              |

Enter command (add/complete/remove/quit):
```

## Implementation Notes
- Use Python's built-in `csv` module for reading and writing the CSV file.
- Implement a simple command parser to handle user input.
- Use the `datetime` module to track dates for adding and completing items.
- Ensure proper error handling for invalid commands or item IDs.
- Implement a clean and efficient way to display items in two columns.

## requirements.txt
Use the following requirements:

```
python-dateutil==2.8.2
prettytable==2.5.0
```

## Future Enhancements (Optional)
- Add due dates for tasks
- Implement priority levels for tasks
- Add search functionality
- Create categories or tags for better organization
- Implement data backup and restore features
