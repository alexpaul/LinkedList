# Node and Linked List

A node is an abstract data structure that consists of a value and next pointer property. 

Node class 

```swift 
class Node {
  var value: Int
  var next: Node?
  init(_ value: Int) {
    self.value = value
  }
}
```

## Write a function to print all the values in a linked node (list)

```swift 
func printNodeValues(node: Node?) {
  var node = node
  while let currentNode = node {
    print(currentNode.value)
    node = currentNode.next
  }
}

printNodeValues(node: node1) // 1 2 3
```

## Write a function to reverse values in a linked node (list) 

```swift 
func reverseList(_ node: Node?) -> Node? {
  var node = node
  var previousNode: Node?
  var nextNode: Node?
  while let currentNode = node {
    nextNode = currentNode.next
    currentNode.next = previousNode
    previousNode = currentNode
    node = nextNode
  }
  return previousNode
}

printNodeValues(node: reverseList(node1)) // 3 2 1
```

## Linked List 

A linked list is a series of connected nodes.  

Types of a linked list: 
* singly linked list 
* doubly linked list 

A linked list has a head and tail property. 

```swift 
class LinkedList {
  private var head: Node?
  private var tail: Node?
  
  var isEmpty: Bool {
    return head == nil
  }
}
```



