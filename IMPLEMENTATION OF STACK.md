# Exp.No:13B
## IMPLEMENTATION OF STACK

---

### AIM  
To write a Python program to implement a stack using a list and its built-in methods (`append()`, `pop()`).

---

### ALGORITHM

1. **Start the program.**
2. **Define a class `st`** with the following methods:
   - `push(self, num)`: Adds the number `num` to the stack.
   - `pop(self)`: Removes and returns the top element from the stack.
3. **Create a stack object `s`** using the class `st`.
4. **Input the stack size**: Take an integer input `size` to define the size of the stack.
5. **Loop through numbers from 1 to size**: Add only the odd numbers to the stack using the `push()` method.
6. **Display the elements** in the stack after the loop completes.
7. **Call `pop()`** to remove the top element from the stack and display the popped element.
8. **Display the stack again** to show the remaining elements.
9. **End the program.**

---

### PROGRAM
```
`stack = []
class st:
    def push(self,L):
        for i in L:
            stack.append(i)
        return
    
    # Write your code here

    def pop(self):
        if stack:
            print("Element popped : ",stack.pop())
        else:
            print("empty")
    
    # Write your code here
   
    def peek(self):
        print("Elements in the stack\n",stack)
    
    # Write your code here
s=st()
a=int(input())
l=[i for i in range(1,a) if i%2!=0]
s.push(l)
s.peek()
s.pop()
s.peek()``


```
# OUTPUT
<img width="1213" height="286" alt="image" src="https://github.com/user-attachments/assets/c7fedd3d-9e12-401f-816e-1e09ac81d65d" />

# RESULT
Thus the program to implement a stack using a list and its built-in methods has been implemented and executed successfully.
