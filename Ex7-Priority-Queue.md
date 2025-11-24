
````
Ex7 Removal of Nodes with a Specific Value from a Linked List
DATE: 22.11.2025
AIM:
To write a java program that removes all nodes from a linked list whose value matches a given integer (val) and returns the new head of the modified linked list.

Algorithm
Create a singly linked list by inserting nodes containing integer values.
Read the value val that needs to be removed from the list.
Skip all matching nodes at the beginning and update the head to the first non-matching node.
Traverse the list; whenever current.next.data == val, bypass that node by linking current.next = current.next.next.
Return and display the updated head of the modified linked list.

````


## Program:
```
public class RemoveNodesFromList {

    // Node class
    static class Node {
        int data;
        Node next;

        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }

    Node head;

    // Insert at end
    public void insert(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            return;
        }
        Node temp = head;
        while (temp.next != null) {
            temp = temp.next;
        }
        temp.next = newNode;
    }

    // Remove nodes equal to val
    public void removeValue(int val) {
        // Remove matching nodes at head
        while (head != null && head.data == val) {
            head = head.next;
        }

        Node temp = head;
        // If list becomes empty after removals
        if (temp == null) return;

        // Remove matching nodes in remaining list
        while (temp.next != null) {
            if (temp.next.data == val) {
                temp.next = temp.next.next;
            } else {
                temp = temp.next;
            }
        }
    }

    // Display list
    public void display() {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " ");
            temp = temp.next;
        }
        System.out.println();
    }

    // Main
    public static void main(String[] args) {
        RemoveNodesFromList list = new RemoveNodesFromList();

        list.insert(10);
        list.insert(20);
        list.insert(20);
        list.insert(30);
        list.insert(20);
        list.insert(40);

        int val = 20;

        System.out.println("Original List:");
        list.display();

        list.removeValue(val);

        System.out.println("List After Removing " + val + ":");
        list.display();
    }
}

```

## Output:

<img width="1328" height="467" alt="image" src="https://github.com/user-attachments/assets/dd318017-5f30-411a-b53d-acffe0d04fb4" />


## Result:
Thus, the C program to display the elements of the priority queue after insertion and deletion operation is implemented successfully
