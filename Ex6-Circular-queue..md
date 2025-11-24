# Ex6 Right Rotation LinkedList
## AIM:
To write a C program to delete three elements from the filled circular queue.

## Algorithm
Create the singly linked list by inserting nodes one by one.
Count the total number of nodes (length) and connect the last node to the head to form a circular list.
Reduce rotations using k = k % length to avoid extra rotations.
Traverse to the (length - k)th node and mark it as the new tail.
Set newHead = newTail.next, break the circular link, and display the rotated linked list.

## Program:
```
/*
import java.util.Scanner;
class RotateLinkedList {
    static class Node {
        int data;
        Node next;
        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }
    public static Node rotateRight(Node head, int k) {
        if (head == null || head.next == null || k == 0) 
            return head;

        Node temp = head;
        int length = 1;
        while (temp.next != null) {
            temp = temp.next;
            length++;
        }
        temp.next = head;
        k = k % length;
        int skip = length - k;

        Node newTail = head;
        for (int i = 1; i < skip; i++) {
            newTail = newTail.next;
        }

        Node newHead = newTail.next;
        newTail.next = null; 

        return newHead;
    }
    public static void display(Node head) {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " ");
            temp = temp.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of nodes: ");
        int n = sc.nextInt();

        Node head = null;
        Node tail = null;

        System.out.println("Enter elements:");
        for (int i = 0; i < n; i++) {
            int val = sc.nextInt();
            Node newNode = new Node(val);

            if (head == null) {
                head = tail = newNode;
            } else {
                tail.next = newNode;
                tail = newNode;
            }
        }

        System.out.print("Enter k (rotate by k positions): ");
        int k = sc.nextInt();

        head = rotateRight(head, k);

        System.out.println("Rotated Linked List:");
        display(head);

        sc.close();
    }
}

*/
```

## Output:

<img width="1322" height="587" alt="image" src="https://github.com/user-attachments/assets/61d8b653-226a-484d-91c1-99aebc82b96c" />


## Result:
Thus, the  program to delete three elements from the filled circular queue is implemented successfully.
