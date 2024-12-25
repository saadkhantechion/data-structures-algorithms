Let's move on to the next data structure.

### 2. **Linked List** (Intermediate)
A **linked list** is a linear data structure where elements (called nodes) are stored in memory, each containing two parts:
1. **Data**: The actual value stored in the node.
2. **Next**: A reference (or pointer) to the next node in the sequence.

Unlike arrays, linked lists do not require contiguous memory locations.

#### Types of Linked Lists:
- **Singly Linked List**: Each node points to the next node in the sequence.
- **Doubly Linked List**: Each node points to both the next and the previous node.
- **Circular Linked List**: The last node points back to the first node.

#### Characteristics:
- Dynamic size (can grow and shrink in size).
- Insertion and deletion can be done efficiently (O(1)) if the position is known.
- Accessing elements is O(n) because you need to traverse from the head to the desired position.

#### Code Example (Singly Linked List in Java):
```java
// Node class to represent each element in the list
class Node {
    int data;
    Node next;
    
    public Node(int data) {
        this.data = data;
        this.next = null;
    }
}

// Linked List class
class LinkedList {
    Node head;

    // Method to add a node at the end of the list
    public void append(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            return;
        }
        Node current = head;
        while (current.next != null) {
            current = current.next;
        }
        current.next = newNode;
    }

    // Method to print the linked list
    public void printList() {
        Node current = head;
        while (current != null) {
            System.out.print(current.data + " ");
            current = current.next;
        }
        System.out.println();
    }
}

public class Main {
    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.append(1);
        list.append(2);
        list.append(3);
        
        list.printList();  // Output: 1 2 3
    }
}
```

#### Operations:
- **Insertion**: O(1) at the beginning, O(n) at the end (if you don't maintain a tail pointer).
- **Deletion**: O(1) if the node is given (e.g., at the start), but O(n) for arbitrary nodes.
- **Access**: O(n) since you need to traverse from the head node.

**Advantages**:
- Dynamic size: No fixed size like arrays.
- Efficient insertion/deletion, especially at the beginning.

**Limitations**:
- Slower access time compared to arrays due to traversal.
- Extra memory used for storing pointers.

Shall we proceed to the next data structure?