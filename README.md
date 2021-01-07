# Node and Linked List

## Node 

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

#### Write a function to print all the values in a linked node (list)

```swift 
func printNodeValues(node: Node?) {
  var node = node
  while let currentNode = node {
    print(currentNode.value) 
    node = currentNode.next // moving to the next node using the `next` pointer
  }
}

printNodeValues(node: node1) // 1 2 3
```

#### Write a function to reverse values in a linked node (list) 

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

#### Define a Linked List

```swift 
struct LinkedList {
  private var head: Node?
  private var tail: Node?
  
  var isEmpty: Bool {
    return head == nil
  }
}
```

#### Write a function to add a value to a linked list  

```swift 
extension LinkedList {
  mutating func append(_ value: Int) {
    // 1
    // create a new node with the value
    let newNode = Node(value)
    // 2
    // if the list is empty create a new node and add to the head and tail
    if isEmpty {
      head = newNode
      tail = newNode
      return
    }
    // if there are more values in the list, we need to have the (last last node point to the new node)
    guard let lastNode = tail else {
      return
    }
    lastNode.next = newNode
    tail = newNode
  }
}

var list = LinkedList() 
list.append(5)
list.append(12)
list.append(0)
list.append(34)
```

#### Write a function to print the values of a linked list

```swift 
extension LinkedList {
  func printList() {
    var head = self.head
    while let currentNode = head {
      print(currentNode.value)
      head = currentNode.next
    }
  }
}
var list = LinkedList() 
list.append(5)
list.append(12)
list.append(0)
list.append(34)

list.printList()
```

#### Challenge - Write a function to remove the last element from a linked list 

<details> 
  <summary>Solution</summary> 

Sorry was hoping you would give it a shot 🥳
  
```swift 
```
  
</details> 

## Challenges 

#### Challenge 1 

[LeetCode - Middle of a Linked List](https://leetcode.com/problems/middle-of-the-linked-list/)


#### Challenge 2 

[LeetCode - Remove Linked List Elements](https://leetcode.com/problems/remove-linked-list-elements/)


