---
title: A Quick Synopsis of Data Structures
date: 2021-07-27 12:00:00 -0400
categories: [Notes]
---

a cheat sheet i wrote for myself :)

<img src="/img/Data Structure Operations.png"/>

###### Image: [Big O Cheat Sheet](https://www.bigocheatsheet.com/)

**NOTE**: I do not show implementation of these data structures, only simple explanations.

## Collections class

The Collections class includes useful methods for data structures, such as the sort() method.

{% highlight java linenos %}
import java.util.Collections;

ArrayList<String> cars = new ArrayList<String>();
// add cars

Collections.sort(cars); // sort cars in alphabetical order
{% endhighlight %}

View the [documentation](https://docs.oracle.com/javase/7/docs/api/java/util/Collections.html) for more info
  
## ArrayList
  
ArrayLists are data structures that add more functionality to normal arrays. Behind the scenes, Arraylists are an array that start bigger than needed, and increase their size when capacity is reached. Because of this, the ArrayList is often bigger than the data contained within it, which could waste memory. 
  
![ArrayList](https://th.bing.com/th/id/OIP.QpYQ78mkfPqx-R6399NT8AHaN4?pid=ImgDet&rs=1)
  
{% highlight java linenos %}
import java.util.ArrayList;

//String, Integer, Boolean, Character, Double, or any other type
ArrayList<String> cars = new ArrayList<String>();
cars.add("Tesla");
cars.get(0);
cars.set(0, "BMW");
cars.remove(0);
cars.clear();
cars.size();
{% endhighlight %}

Pros: Dynamic in size, Rapid access to data O(1), Access random items
  
Cons: Slow insertion/deletion (must recreate array), Uses extra memory

## LinkedList (Singly LinkedList, SLL)

Using a LinkedList is identical to how you'd use an ArrayList, but they are coded differently. While an ArrayList uses an array to store data, LinkedList store data in objects, with a reference to the next link.
  
<img src="/img/LinkedList-implemenation-java.png"/>
  
###### Image: [Programiz](https://www.programiz.com/java-programming/linkedlist)

Same code as ArrayList, but with "LinkedList" instead.
  
Pros: Great insertion/deletion
  
Cons: No random access, Slow access

## Doubly Linked List

  Doubly Linked List are similar to SLL's except each node contains a reference to the previous node in addition to a next. 
  
  ![DLL](https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2014/03/DLL1.png)
  
  Pros: Can traverse backwards, Insertion/Deletion may be faster

  Cons: Uses more memory, obviouslly

## Circular Linked List
  
  Circular Linked List can be either SLL's or DLL's. A CLL is one where the last node has a reference to the first node, creating a circle.
  
  Single:
  
  ![CSLL](https://media.geeksforgeeks.org/wp-content/uploads/CircularLinkeList.png)

  Double:
  
![CDLL](https://media.geeksforgeeks.org/wp-content/uploads/Circular-doubly-linked-list.png)
  
###### Image: [Geeks4Geeks](https://www.geeksforgeeks.org/)
  
## XOR Linked List
  
  who the heck knows but it sounds epic
  
  memory efficient DLL because it only needs 1 reference to both prev and next?!?! what???
  
## HashMap
  
  Rather than store data as an array, HashMaps allow you to store data in a key/value pair. (A dictionary)

{% highlight java linenos %}
import java.util.HashMap;
  
  HashMap<String, Integer> points = new HashMap<String, Integer>();
  points.put("Amy", 154); // add amy 154
  points.put("Dave", 42); // add dave 42
  points.remove("Amy"); // remove amy 154
  points.get("Dave"); // 42
  points.containsKey("Amy"); // False
  points.containsValue("42"); // True
  
{% endhighlight %}

Pros: A unique data structure for specific uses
  
  Cons: Cannot hold duplicate keys. Will delete the previous if attempted.
  
## HashSets
  
  A Set is a data structure that cannot contain duplicate values.

{% highlight java linenos %}
import java.util.HashSet;
  
  HashSet<String> set = new HashSet<String>();
  set.add("A");
  set.add("B");
  int s = set.size();
  set.contains("C") // false
  
{% endhighlight %}

  Pros: Its a set

Cons: Do not maintain order (A LinkedHashSet can be used for this) 
  
## Hash Table & Functions
  
  A Hash Table is a data structure based on an array. HashTables store elements based on a HashFunction. The HashFunction decides where the element should go in the HashTable. The HashFunction itself does the calculation.
  
  Imagine an array of size 10 where each element is initalized to null. Now lets say you want to add the value 5 to this array. A HashFunction may decide to do array[5] = 5. This is not a good HashFunction, but still a good example to introduce the concept. A HashFunction simply decides where an element should go in a HashTable based on a calculation. Because of this, there cannot be duplicates. And the HashFunction has to be careful to respect the restraints of the size of the HashTable.
  
  [This video](https://youtu.be/B4vqVDeERhI) by Derek Banas explains this much better than I could ever type.
  
  If you ever tried inserting a value into an index that was already taken, you'd have to handle that "collision". Again, its up to the HashFunction to decide how thats handled. You could try inserting it into ++index, for example.
  
  By reversing the calculation done on the element, you can find it's index in the array very quickly. 
  
  Pros: Fast search
  
  Cons: I assume that the more collisions you have to deal with, the less efficient searching is. So the hashfunction has to be good.
  
## Stacks
  
Stacks are a linear data structure that hold objects in a "line". Follows the rule of LIFO (Last In First Out). You place objects "on top of eachother", and take them out from the top. An empty stack has a top value of -1. 

  ![Stack](https://static.javatpoint.com/core/images/java-stack.png)
  
###### Image: [Javatpoint](https://www.javatpoint.com/java-stack#:~:text=Java%20Stack%20The%20stack%20is%20a%20linear%20data,and%20classes%20to%20store%20the%20collection%20of%20objects.)
  
{% highlight java linenos %}

  import java.util.Stack;
  
  Stack myStack = new Stack();
  // Stack<type> myStack = new Stack<>();
  
  myStack.push(81); // add
  myStack.push(16); // add
  
  boolean result = myStack.empty(); // check if empty
  
  int x = myStack.pop(); // remove and return
  int y = myStack.peek(); // view but not remove
  
  int location = myStack.search(100); // return index, or -1 if not found
  
  int size = myStack.size(); // get size
  
{% endhighlight %}

This is a unique type of data structure. Use when you need the LIFO structure. Do note the time complexity, O(1) insertion/deletion.
  
## Queues
  
Like Stacks, Queues are a linear data structure that hold objects in a "line". However, they follow the rule of FIFO (First In First Out). Similar to how a line at a store works, the first person in the line is the first person served.

{% highlight java linenos %}

  import java.util.LinkedList;
  import java.util.Queue;
  
  Queue<Integer> q = new LinkedList<>();
  
  q.add(43); // add
  q.add(8); // add

  int x = q.remove(); // remove and return
  int y = q.peek(); // view but not remove
  
  int size = q.size(); // get size
  
{% endhighlight %}

Like Stacks, Queues are a unique type of data structure. Use when you need the FIFO structure. Note the time complexity as well.

## Priority Queue

A priority queue is a queue that follows a comparable priority, rather than FIFO. Objects of the priority queue MUST be comparable. 

{% highlight java linenos %}

  PriorityQueue<Integer> pQ = new PriorityQueue<Integer>();
  
  // add items
  pQ.add(4);
  pQ.add(99);
  pQ.add(17);
  
  // pQ is [4, 17, 99]
  
  int x = pQ.peek(); // view but not remove (4)
  
  int y = pQ.poll(); // remove and return (4)
  
  pQ.remove(4);
  
  int y = pQ.poll(); // 17
  
  // other methods:
  // clear();
  // contains(element);
  // and more
  
{% endhighlight %}

Note: By implementing Comparable you can make your own classes comparable. 

## Graphs & Graph Theory
  
From mathematics, "a graph G is defined as a set of vertices (V) and edges (E) that connects vertices." Graphs have huge applications in computer science, and there is a lot to know about them.
  
[This video](https://www.youtube.com/watch?v=LFKZLXVO-Dg) is a great introduction from a computer science perspective. There is a lot of terminology to know. This isn't as much about programming as it is mathematics. 
  
[Javatpoint](https://www.javatpoint.com/java-graph) has this in words.

# Trees
  
A Tree is a non-linear data structure consisting of nodes, usually organized hierarchy. Each node may contain children nodes.
  
![Tree](https://th.bing.com/th/id/R.613d809fcd0f0feeee1bfeb2627ca06f?rik=DBXVkH%2fcTEsgfg&riu=http%3a%2f%2fwww.chercher.tech%2fjava-data-structures%2fimages%2ftrees-java-data-structures.png&ehk=itj2JESCDqxXyyPj5Kdf90hG8bNscZlz4S1rTc192PM%3d&risl=&pid=ImgRaw&r=0)
  
A **Binary Tree** is a tree in which each node contains between 0 and 2 child nodes. That is, they can have right and left child nodes, or neither, or one. The photo above is a binary tree.
  
## Binary Search Tree
  
A binary search tree is a binary tree where the right child node is bigger than the parent node, and the left child node is smaller than the parent node.
  
Heres a [video](https://www.youtube.com/watch?v=oSWTXtMglKE) on the code implementation, and some concepts.
  
The concepts are:

### Unbalanced vs Balanced

Balanced trees make sure each side have an equal amount of nodes. This makes finding a node must faster, as it can cut the possibilites in half (O(logn))
  
![Balanced vs Unbalanced](https://cdn-images-1.medium.com/max/1600/1*zkYif_uQsOS80Zx7L0K9pg.jpeg)
  
## Inorder vs Preorder vs Postorder Traversal

Inorder traversal will actually print the tree in numerical order.
  
![ordering](https://camo.githubusercontent.com/13385d3385ff1d10cd660824d9771f9a91207d1e0fcb059b88df27f7257f8b0e/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f3835393832353830323131303935393634362f3837323633303432313139383836383530302f756e6b6e6f776e2e706e67)

## B-Tree & B+ Tree

A B-Tree is a self balancing tree. Nodes contains more than just 1 value, it could contain many, depending on the order of the tree. Let's say we have a B-Tree of order 3. There can be at max 2 values in each node. Each node can have at max 3 children. There are many rules for B-Trees.
  
[this video](https://www.youtube.com/watch?v=C_q5ccN84C8) is a very good introduction
  
[this article](https://www.javatpoint.com/b-tree) is a good read
  
### B+ Tree
 
A B-Tree, except values can only be accessed from the leaf nodes. The leaf nodes are connected together. SUPER COMPLICATED?
  
[HERES AN ARTICLE](https://www.javatpoint.com/b-plus-tree)
  
## Max & Min Heaps
  
A Max Heap is a tree-like data structure in which each node is greater than or equal to its children nodes. [This video](https://www.youtube.com/watch?v=eFCn6udv3gQ) explains it well. (with implementation)
  
A Min Heap is similar, but each node is smaller than or equal to its children node.

![MaxHeap](https://media.geeksforgeeks.org/wp-content/uploads/MaxHeap.png)

###### Image: [GeeksForGeeks](https://www.geeksforgeeks.org/max-heap-in-java/)

{% highlight java linenos %}
// Some notes on heaps from GeeksForGeeks
  
// typically represented as an array
// root element will be at array[0]
// if a node is stored an index k, then:
  // left child is stored at index 2k+1
  // right child is stored at index 2k+2
  
{% endhighlight %}

Pros: Fast insertion/deletion, fast sorting

Cons: Slow searching

## AVL Trees
  
AVL Trees are Binary Search Trees (BST) that are strictly height-balanced. This means the left side of the root will always be equal to the right side, and at most there will be a difference of 1 or -1. It does this by applying rotations to the tree.
  
[heres](https://www.tutorialspoint.com/data_structures_algorithms/avl_tree_algorithm.htm) a great explanation

## Red-Black Tree
  
Red-Black Trees are similar to AVL trees, except they are not always perfectly balanced. An AVL tree demands that the difference be no greater than 1, but Red-Black trees break these rules.

These work by assigning each node a color. Black implies that the nodes to the left and right are balanced. Red implies the opposite. Whenever there is a red-red child-parent relationship, rotations are applied. (there are exceptions though, read the link below)
  
[heres](https://www.javatpoint.com/red-black-tree) a great explanation
  
## Splay Trees
  
are a thing, go google it. [zig zag](https://www.geeksforgeeks.org/splay-tree-set-1-insert/#:~:text=1%20Splay%20trees%20have%20excellent%20locality%20properties.%20Frequently,can%20change%20even%20with%20read-only%20operations%20like%20search.)
  
"The main idea of splay tree is to bring the recently accessed item to root of the tree, this makes the recently searched item to be accessible in O(1) time if accessed again." The 80/20 rule is the idea behind this tree being so good. 80% of access is to 20% of data. 

## KD-Tree of K Dimension
  
ok so these are really complicated. [heres](https://www.youtube.com/watch?v=XG4zpiJAkD4) the best explanation on youtube. basically, each level of the tree takes focus on a different dimension, alternating between these dimensions. At the root level, you may compare x, but the children compare y, and those children compare z. The children after that may compare x again, and so forth and so on.
