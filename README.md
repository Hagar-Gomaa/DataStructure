
# Data Structures

This repo provides the basic requirements to understand and implement these data structures .

# Table of Content

- [Array](#array)
- [Linked-List](#Linked-List)
- [Stack](#stack)
- [Queue](#queue)
- [Hash Table](#hash-table)
- [Tree](#Tree)
- [Binary Search Trees](#Binary-Search-Trees )

## Array

> An Array is a linear collection of elements,  
where the elements can be accessed via indices,  
which are usually integers used to compute offsets

Arrays are one of the more contentious data structures as they have a variety 
of different implementations. For example, an 
Array has a specific "set-size" data structure (meaning it can't expand beyond 
its set dimensions and this might conflict with many reader's understanding of 
a typical Array), and this data structure can be the basis of other data structures 
such as Lists and Strings.

But what I have found in many languages is that the Array data structure is 
implemented using *other* data structures such as a Dictionary (or Object/Hash 
Table depending on your background), Linked List and even Search Trees.


- `index` (return index of specified element)
- `pop` (remove last element)
- `push` (append new element)
- `shift` (remove first element)
- `unshift` (prepends new element)


# Linked-List

A List is a simple collection of elements, which is different from an Array in 
that the elements within the List can only be accessed by looping through the 
entire list searching for the element of interest.

The Linked-List is made up of a collection of "nodes". Each node will hold:

- data for the current node
- pointer to the next node

 Linked List, meaning each node is linked to the 
next node (hence there is no index access). The starting node is referred to as 
the "head" and then from the head you can loop iteratively through each node.

There are also different types of Linked List, the standard type is a "singly" 
Linked List, where by the last node's pointer will point to `null` (to indicate 
the end of the list). But there is also a "doubly" Linked List which allows each 
node's pointer to point to the *previous* node (not just point to the following node).

> Note: the following API is based on the "singly" Linked List

There are also "circularly" Linked Lists which simply loop around and around the 
data structure (i.e. when it reaches the last node, the pointer will point 
to the starting node and vice-versa for the first node moving backwards).

When inserting items, for performance, new items are inserted before the node at the head



- `insert` (prepend new element or insert new element at specified index)
- `remove` (remove element at specified index)
- `clear` (remove all elements from the list, leaving an empty list)
- `next` (move to next item in the list)
- `move_to` (move to specified index)
- `position` (returns the current index position)
- `get` (returns the element at the specified index)
- `front` (change index position to be the starting position)
- `end` (change index position to be the ending position)
- `next?` (returns Boolean value checking if a next index exists)



---

## Stack

> A stack is a list of elements that are accessible only  
from one end of the list, which is called the `top`  
For example, the stack of trays at a cafeteria.  
Trays are always removed from the top,  
and when trays are put back on the stack after being washed,  
they are placed on the top of the stack

Because this data structure is LIFO (Last In, First Out) it means that you can 
only ever access the element that is on the top of the stack. If you want to 
access an element further down the stack then you'll need to remove the elements 
that currently sit above it.

 
Example:

Stack -> `[h, e, l, l, o]` when `pop`'ed into an Array would look like `[o, l, l, e, h]` where we 
can see the word "hello" **isn't** a palindrome. But if we try again using the word "dad": 
`[d, a, d]`, we can see that you end up with a new Array `[d, a, d]` which **is** 
the same word.



- `pop` (remove top element)
- `push` (append new element)
- `peek` (return the top element but don't `pop` it from the Stack)
- `clear` (remove all elements from the Stack, leaving an empty Stack)

### Properties

- Sequential/Ordered (i.e. consistent element ordering based on collection population)
- LIFO (Last In, First Out)

### Usefulness

- Useful when the order of your data matters
- Useful for searching the collection for specific data
- Fast (as Stacks only allows `push` and `pop` functionality)
- Used a lot in underlying language implementations (e.g. expression evaluation and handling function calls)

---

## Queue

> A queue is a type of list where data is  
inserted at the end and is removed from the front.  
Queues are used to store data in  
the order in which they occur, as opposed to a stack,  
in which the last piece of data entered  
is the first element used for processing

> Think of a queue like the line at your bank,  
where the first person into the line  
is the first person served,  
and as more customers enter a line,  
they wait in the back until it is their turn to be served


### API

- `enqueue` (append new element)
- `dequeue` (remove first element)
- `peek` (return the first element but don't `dequeue` it from the Queue)
- `clear` (remove all elements from the Queue, leaving an empty Queue)

### Properties

- Sequential/Ordered (i.e. consistent element ordering based on collection population)
- FIFO (First In, First Out)

### Usefulness

- Processing data that needs to be handled in a sequential order
- Can be useful for sorting data (depending on the sort)


## Hash Table

A Hash Table is fundamentally an Dictionary data structure. The keys for the 
Dictionary are determined by a function that creates a hash of the key's 
associated data.


The "hash value" (as seen in the table matrix above) is the key we'll use to store 
our data under within our Dictionary. What you should also notice is there is a collision 
between our indices. The combination of the data "Mark" and "kraM" used with our 
particular algorithm has demonstrated that we have a collision that needs to be 
resolved somehow (we'll come back to this).

> Note: I'm using a Dictionary in this explanation  
but if your language's implementation of an Array  
allows any type of data for its indices then you  
should really use an Array instead.

### What data structure *should* I use?

For the purposes of the implementation code in this repo I've decided to use an 
Array and to make sure that, regardless of the data, my hashing algorithm generates 
a numerical value.

The reason for this is simply because the work around for collisions are centered 
around the data structure being an Array.


---

## Tree

A Tree data structure is used to store hierarchical data (it is non-linear), 
such as an Operating System file system.

A Tree contains "nodes" (a node has a value associated with it) and each node is 
connected by a line called an "edge". These lines represent the relationship 
between the nodes.

The top level node is known as the "root" and a node with no children is a "leaf".

If a node is connected to other nodes, then the preceeding node is referred to 
as the "parent" and nodes following it are "child" nodes.

### Binary Trees

There is a specific type of tree referred to as a "Binary Tree", which restricts 
its child nodes to no more than two.

The children of a node are referred to as the "left" node and the "right" node.

When creating a Binary Tree object you'll pass in the first node to become the 
root node and each node is itself an object with an associated value, along with 
a left and right node linked to.

### Binary Search Trees  

There is another type of tree called a "Binary Search Tree" and this is an 
extension of the Binary Tree, with the addition that the child nodes are stored 
in a specific order depending on a custom calculation.

The calculation is very simple: if a node has a lesser value than its parent it 
is placed in the "left" node position. If on the other hand it has a greater value 
than its parent it is placed in the "right" node position.




> Note: traversal methods rely on recursion  
and need to be carefully implemented to ensure  
they do not cause a Stack Overflow error




