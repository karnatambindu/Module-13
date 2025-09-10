# Exp.No:13E 
## TOWER OF HANOI

---

### AIM  
To write a Python program to implement **Tower of Hanoi** and display all the moves of the disks using a recursive function.  
Consider the names of the tower pegs as A, B, C. Get the number of disks value from the user.

---

### ALGORITHM  

1. **Start the program.**
2. **Input** the number of disks `n`.
3. **Print** the number of disks.
4. Define a **recursive function** `TowerOfHanoi(n, source, destination, auxiliary)`:
   - If `n == 1`:
     - Print: "Move disk from source to destination".
   - Else:
     - Call `TowerOfHanoi(n - 1, source, auxiliary, destination)`  
       → Move `n-1` disks from source to auxiliary using destination as helper.
     - Print: "Move disk from source to destination"  
       → Move the largest disk to the destination.
     - Call `TowerOfHanoi(n - 1, auxiliary, destination, source)`  
       → Move `n-1` disks from auxiliary to destination using source as helper.
5. Call `TowerOfHanoi(n, 'A', 'C', 'B')` to start the process.
6. **End the program.**

---

### PROGRAM  

```
def TowerOfHanoi(n, source, destination, auxiliary):
    if (n > 0):
        TowerOfHanoi(n-1, source, auxiliary, destination)   # Step 1: move n-1 disks
        print("Move disk from", source, "to", destination)  # Step 2: move the nth disk
        TowerOfHanoi(n-1, auxiliary, destination, source)   # Step 3: move n-1 disks

n = int(input())
print("No. of disks =", n)

```

### OUTPUT
<img width="968" height="933" alt="image" src="https://github.com/user-attachments/assets/910433d9-daa1-4e83-9f54-adbc8ef82df7" />


### RESULT
Thus the program to implement Tower of Hanoi has been implemented and executed successfully.
