# Introduction to stack

A stack is an ordered collection of items where the addition of new items and the removal of existing items always takes place at the same end. This end is commonly referred to as the “top”, and the opposite end is known as the “base”.

Items that are closer to the base have been in the stack the longest. The most recently added item is always on the top of the stack and thus will be removed first. The stack provides an ordering based on length of time in the collection; the “age” of any given item increases as you move from top to base.

There are many examples of stacks in everyday situations. Consider a stack of plates on a table, where it’s only possible to add or remove plates to or from the top. Or imagine a stack of books on a desk. The only book whose cover is visible is the one on top. To access the others, we must first remove the ones sitting on top of them.

# Time complexity

empty() – Returns whether the stack is empty – Time Complexity: O(1)
size() – Returns the size of the stack – Time Complexity: O(1)
top() – Returns a reference to the topmost element of the stack – Time Complexity: O(1)
push(a) – Inserts the element ‘a’ at the top of the stack – Time Complexity: O(1)
pop() – Deletes the topmost element of the stack – Time Complexity: O(1)

# Implementation: 

There are two ways to implement a stack: 

Using array
Using linked list

using array

``` 
# Python program for implementation of stack

# import maxsize from sys module
# Used to return -infinite when stack is empty
from sys import maxsize

# Function to create a stack. It initializes size of stack as 0
def createStack():
	stack = []
	return stack

# Stack is empty when stack size is 0
def isEmpty(stack):
	return len(stack) == 0

# Function to add an item to stack. It increases size by 1
def push(stack, item):
	stack.append(item)
	print(item + " pushed to stack ")
	
# Function to remove an item from stack. It decreases size by 1
def pop(stack):
	if (isEmpty(stack)):
		return str(-maxsize -1) # return minus infinite
	
	return stack.pop()

# Function to return the top from stack without removing it
def peek(stack):
	if (isEmpty(stack)):
		return str(-maxsize -1) # return minus infinite
	return stack[len(stack) - 1]

# Driver program to test above functions
stack = createStack()
push(stack, str(10))
push(stack, str(20))
push(stack, str(30))
print(pop(stack) + " popped from stack")

```

```
10 pushed into stack
20 pushed into stack
30 pushed into stack
30 Popped from stack
Top element is : 20
Elements present in stack : 20 10  
```
 Pros: Easy to implement. Memory is saved as pointers are not involved. 
Cons: It is not dynamic. It doesn’t grow and shrink depending on needs at runtime.
 Implementing Stack using Linked List:
 ```
 # Python program for linked list implementation of stack

# Class to represent a node


class StackNode:

	# Constructor to initialize a node
	def __init__(self, data):
		self.data = data
		self.next = None


class Stack:

	# Constructor to initialize the root of linked list
	def __init__(self):
		self.root = None

	def isEmpty(self):
		return True if self.root is None else False

	def push(self, data):
		newNode = StackNode(data)
		newNode.next = self.root
		self.root = newNode
		print "% d pushed to stack" % (data)

	def pop(self):
		if (self.isEmpty()):
			return float("-inf")
		temp = self.root
		self.root = self.root.next
		popped = temp.data
		return popped

	def peek(self):
		if self.isEmpty():
			return float("-inf")
		return self.root.data


# Driver code
stack = Stack()
stack.push(10)
stack.push(20)
stack.push(30)

print "% d popped from stack" % (stack.pop())
print "Top element is % d " % (stack.peek())

# This code is contributed by Nikhil Kumar Singh(nickzuck_007)

```
```
10 pushed to stack
20 pushed to stack
30 pushed to stack
30 popped from stack
Top element is 20
Elements present in stack : 20 10 
```
# Advantages and Disadvantages of Stack

A Stack is a simple data structure for storing data.

In stack, the order in which the data arrives is important. Stacks are ideal for enforcing sequential rules of access ie, LIFO.

A Bunch of plates are the siples examples of stack.

Stacks are used for reversing things. If you push something, say a String onto a Stack one character at a time, and then construct a String from the members popped off the Stack, then the String is reversed.

ADVANTAGES

Easy to started
Less Hardware Requirement
Cross- Platform
DIS ADVANTAGES

not flexible
Lack of scailability
Unable to Copy & Paste