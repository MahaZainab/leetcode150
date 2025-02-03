# Linked List Tutorial

Welcome to this tutorial on linked lists! This document will guide you through the fundamentals of linked lists, a popular data structure used in computer science for managing collections of elements dynamically.

## What is a Linked List?

A linked list is a linear data structure that consists of a sequence of elements called nodes. Each node contains two parts:
- **Data**: The actual data stored in the node.
- **Next**: A reference to the next node in the list.

Linked lists are different from arrays as they are not stored contiguously in memory, which allows for efficient insertions and deletions.

## Advantages of Linked Lists

- **Dynamic Size**: Automatically resizes depending on the number of elements.
- **Ease of Insertion/Deletion**: Nodes can easily be added or removed without reorganizing the entire data structure.

## Core Operations

- **Insertion**: Add new nodes to the list.
- **Deletion**: Remove nodes from the list.
- **Traversal**: Go through each node in the list.
- **Search**: Find a node containing a given value.
- **Update**: Modify the data of an existing node.

## Implementation in Python

Here's a basic implementation of a singly linked list in Python:

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def print_list(self):
        temp = self.head
        while temp:
            print(temp.data, end=' -> ')
            temp = temp.next
        print('None')

    def append(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
            return
        last = self.head
        while last.next:
            last = last.next
        last.next = new_node

    def insert_after(self, prev_node, data):
        if not prev_node:
            print("The given previous node must inLinkedList.")
            return
        new_node = Node(data)
        new_node.next = prev_node.next
        prev_node.next = new_node

    def delete_node(self, key):
        temp = self.head

        if (temp is not None):
            if (temp.data == key):
                self.head = temp.next
                temp = None
                return

        while(temp is not None):
            if temp.data == key:
                break
            prev = temp
            temp = temp.next

        if(temp == None):
            return

        prev.next = temp.next
        temp = None
