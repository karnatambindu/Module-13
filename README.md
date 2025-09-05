# Exp.No:32 CONVERSION OF INFIX TO POSTFIX
# AIM
To write a Python program to convert a given Infix expression to Postfix expression by following the precedence and associative rules. The input expression contains only Division, Subtraction, and Bitwise AND operators. A dictionary is used to set the priority for operators, and a set is used to hold the operators used in the given expression.
# ALGORITHM
Start the program.
Initialize an empty stack and an empty output string.
Iterate through each character in the infix expression:
If the character is not an operator, append it directly to the output string.
If the character is an open parenthesis '(', push it onto the stack.
If the character is a close parenthesis ')', pop from the stack and append to the output until encountering a left parenthesis '('.
If the character is an operator, handle it based on precedence:
While there’s an operator at the top of the stack with higher or equal precedence, pop the stack and append those operators to the output.
Push the current operator onto the stack.
Use a priority dictionary to define operator precedence, ensuring higher precedence operators are placed before lower precedence ones.
Once the expression is fully processed, continue popping any remaining operators from the stack and append them to the output.
Return the final postfix expression.
Print the result.
End the program.
# PROGRAM
```
OPERATORS = set(['&','-','/','(',')'])
PRIORITY = {'&':1,'-':2,'/':3}

def infixToPostfix(expression):
    stack = []
    output = ''

    for character in expression:
        if character not in OPERATORS:            # if operand (A, B, etc.)
            output += character
        elif character == '(':                    # opening parenthesis
            stack.append('(')
        elif character == ')':                    # closing parenthesis
            while stack and stack[-1] != '(':
                output += stack.pop()
            stack.pop()                           # remove '('
        else:                                     # operator case
            while stack and stack[-1] != '(' and PRIORITY[character] <= PRIORITY[stack[-1]]:
                output += stack.pop()
            stack.append(character)

    while stack:                                  # pop remaining operators
        output += stack.pop()

    return output

expression = input()
print("infix notation: ", expression)
print("postfix notation: ", infixToPostfix(expression))
```
# OUTPUT
<img width="1178" height="232" alt="Screenshot 2025-09-05 221901" src="https://github.com/user-attachments/assets/e62ee66d-bc53-4618-ae62-99df6e4dbc10" />

# RESULT
Thus the python program to convert infix to postfix expression has been implemented and executed successfully.

# Exp.No:31  IMPLEMENTATION OF STACK
AIM
To write a Python program to implement a stack using a list and its built-in methods (append(), pop()).
# ALGORITHM
Start the program.
Define a class st with the following methods:
push(self, num): Adds the number num to the stack.
pop(self): Removes and returns the top element from the stack.
Create a stack object s using the class st.
Input the stack size: Take an integer input size to define the size of the stack.
Loop through numbers from 1 to size: Add only the odd numbers to the stack using the push() method.
Display the elements in the stack after the loop completes.
Call pop() to remove the top element from the stack and display the popped element.
Display the stack again to show the remaining elements.
End the program.
# PROGRAM
```
stack = []
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
s.peek()
```
# OUTPUT
<img width="1213" height="286" alt="Screenshot 2025-09-05 222303" src="https://github.com/user-attachments/assets/8e17669e-e105-41dd-b548-a33718d82c92" />
# RESULT
Thus the program to implement a stack using a list and its built-in methods has been implemented and executed successfully.

# Exp.No:33 POSTFIX EVALUATION

# AIM 
To write a Python program to evaluate a user-given Postfix expression that contains Multiplication and Addition operators using the stack concept.
# ALGORITHM
Start the program.
Define a set named OPERATORS containing all the valid operators: *, +, **, -, /, %.
Define a function evaluate_postfix(exp) to evaluate the postfix expression:
Inside the function, create an empty list called stack to store operands and intermediate results.
Loop through each item in the given postfix expression:
If the current item is not in OPERATORS, it is an operand, so append it to the stack.
If the current item is an operator:
Pop the top two elements from the stack (first pop is a, second pop is b).
Perform the operation b <operator> a depending on the current operator.
Store the result in a variable called result.
Append the result back to the stack.
After the loop ends, return the first element of the stack as the final evaluation result.
Take a postfix expression as input from the user.
Print the postfix expression.
Call the function evaluate_postfix() with the input and print the result.
End the program.
# PROGRAM
```
OPERATORS=set(['*','+']) 


def evaluate_postfix(expression):
    stack=[] 
    for i in expression:
        if i not in OPERATORS:
            stack.append(i)  
        
        else:
            a=stack.pop()  
            b=stack.pop()
        
            if i=='+':
                res=int(b)+int(a)  
            elif i=='*':
                res=int(b)*int(a)
            
            stack.append(res) 
    return stack[0]

expression = input()
print('postfix expression: ',expression)
print('Evaluation result: ',evaluate_postfix(expression))
```

# OUTPUT
<img width="1200" height="226" alt="Screenshot 2025-09-05 223050" src="https://github.com/user-attachments/assets/cb273ba3-fa4b-444c-b2c4-96a2e6855539" />

# RESULT
Thus the program to evaluate a user-given Postfix expression has been implemented and executed succesfully.

# Exp.No:34 PREFIX EVALUATION
# AIM
To write a Python program to evaluate a user-given Prefix expression using a stack. The expression must contain operators such as Multiplication, Addition, and Subtraction.

# ALGORITHM
Start the program.
Define a set of valid operators: *, -, +, %, /, **.
Initialize an empty stack.
Traverse the prefix expression from right to left:
If the character is a digit, convert it to an integer and push it onto the stack.
If the character is an operator, pop two elements from the stack.
Apply the operator on the two popped operands.
Push the result back onto the stack.
If an invalid character is encountered, raise an error.
After traversal, the stack should contain only one element.
Return the single element as the evaluation result.
End the program.
# PROGRAM
```
OPERATORS=set(['*','-','+','%','/','**']) 

def evaluate(expression):
	
	stack = []


	for c in expression[::-1]:

		
		if c not in OPERATORS:
			stack.append(int(c))

		else:
			
			
			o1 = stack.pop()
			o2 = stack.pop()

			if c == '+':
				stack.append(o1 + o2)

			elif c == '-':
				stack.append(o1 - o2)

			elif c == '*':
				stack.append(o1 * o2)

			elif c == '/':
				stack.append(o1 / o2)

	return stack.pop()
test_expression = input()
print("Prefix Expression :",test_expression)
print("Evaluation result :",evaluate(test_expression))
```
# OUTPUT
<img width="749" height="229" alt="Screenshot 2025-09-05 223349" src="https://github.com/user-attachments/assets/562a09cc-7931-4ae7-9253-28e0862de607" />
# RESULT
Thus the program to evaluate a user-given Prefix expression using a stack has been implemented and executed successfully.

# Exp.No:35 TOWER OF HANOI
# AIM
To write a Python program to implement Tower of Hanoi and display all the moves of the disks using a recursive function.
Consider the names of the tower pegs as A, B, C. Get the number of disks value from the user.

# ALGORITHM

Start the program.
Input the number of disks n.
Print the number of disks.
Define a recursive function TowerOfHanoi(n, source, destination, auxiliary):
If n == 1:
Print: "Move disk from source to destination".
Else:
Call TowerOfHanoi(n - 1, source, auxiliary, destination)
→ Move n-1 disks from source to auxiliary using destination as helper.
Print: "Move disk from source to destination"
→ Move the largest disk to the destination.
Call TowerOfHanoi(n - 1, auxiliary, destination, source)
→ Move n-1 disks from auxiliary to destination using source as helper.
Call TowerOfHanoi(n, 'A', 'C', 'B') to start the process.
End the program.
# PROGRAM
```
def TowerOfHanoi(n, source, destination, auxiliary):
    if (n > 0):
        TowerOfHanoi(n-1, source, auxiliary, destination)   # Step 1: move n-1 disks
        print("Move disk from", source, "to", destination)  # Step 2: move the nth disk
        TowerOfHanoi(n-1, auxiliary, destination, source)   # Step 3: move n-1 disks

n = int(input())
print("No. of disks =", n)
```
# OUTPUT
<img width="968" height="933" alt="Screenshot 2025-09-05 223736" src="https://github.com/user-attachments/assets/d9e5f554-83cd-4bd3-9869-966a394c6ff5" />
# RESULT
Thus the program to implement Tower of Hanoi has been implemented and executed successfully.


