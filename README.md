# Ex.No: 1  Implementation of HotPotato game using Queue 
### DATE:                                                                            
### REGISTER NUMBER : 
### AIM: 
To write a python program to simulate the process of passing an item among players and eliminating players based on the given rules until a single winner is determined.
### Algorithm:
1. Initialize the Queue: Create a queue and enqueue all the participants.
2. Pass the Potato: Dequeue the first person in the queue and enqueue them at the end. This simulates passing the potato.
3. Count the Passes: Repeat the passing for a given number of times.
4. Eliminate the Holder: After the set number of passes, remove the person who holds the potato (dequeue the front of the queue).
5. Repeat: Continue the process until only one person remains in the queue.
### Program:
~~~
import queue
import random
import time

def hot_potato(names, num):
    sim_queue = queue.Queue()

    for name in names:
        sim_queue.put(name)

    while sim_queue.qsize() > 1:
        for _ in range(num):
            sim_queue.put(sim_queue.get())
        eliminated = sim_queue.get()
        print(f"{eliminated} is eliminated!")

    return sim_queue.get()

def main():
    players = ["Alice", "Bob", "Charlie", "David", "Eve"]
    #num_passes = random.randint(1, 10)
    num_passes = 1
    print("Hot Potato Game Start!")
    time.sleep(1)
    winner = hot_potato(players, num_passes)
    print(f"\nThe winner is: {winner}")

if __name__ == "__main__":
    main()


~~~










### Output:
![exp1](https://github.com/user-attachments/assets/a0da318c-dab4-4c14-accf-14862098d253)



### Result:
Thus the simple HotPotato game was implemented using Queue.

# Ex.No: 2 Implementation of Stack Plate game using Queue 
### DATE:                                                                            
### REGISTER NUMBER : 
### AIM: 
To write a python program to simulate the process of stacking plates.
### Algorithm:
1. Initialize the Stack
2. Create an empty list to represent the stack.
3. Push the plate on top of stack
4. Pop the plate from top.
5. Display the plate details.
6. Create an interactive menu and display it.
### Program:
~~~
class PlateStack:
    def __init__(self):  # Corrected to use double underscores
        self.stack = []

    def is_empty(self):
        return len(self.stack) == 0

    def push(self, plate):
        self.stack.append(plate)
        print(f"Plate '{plate}' added to the stack.")

    def pop(self):
        if self.is_empty():
            print("The stack is empty. No plates to remove.")
        else:
            removed_plate = self.stack.pop()
            print(f"Plate '{removed_plate}' removed from the stack.")

    def view_stack(self):
        if self.is_empty():
            print("The stack is empty.")
        else:
            print("Current stack of plates:")
            for plate in reversed(self.stack):
                print(plate)

def plate_stack_game():
    plate_stack = PlateStack()
    print("Welcome to the Plate Stack Game!")

    while True:
        print("\nChoose an option:")
        print("1. Add a plate")
        print("2. Remove a plate")
        print("3. View stack")
        print("4. Exit")

        choice = input("Enter your choice: ")

        if choice == '1':
            plate = input("Enter the name of the plate to add: ")
            plate_stack.push(plate)
        elif choice == '2':
            plate_stack.pop()
        elif choice == '3':
            plate_stack.view_stack()
        elif choice == '4':
            print("Exiting the game. Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":  # Corrected to use double underscores
    plate_stack_game()

~~~










### Output:
![exp2](https://github.com/user-attachments/assets/91bde930-6c94-4539-ac09-e1271448eabf)



### Result:
Thus the simple Stack plate game was implemented using data structure Stack.
