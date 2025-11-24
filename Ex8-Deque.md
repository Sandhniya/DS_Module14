```

#Ex8 Detection of Cycle and Finding the Starting Node in a Linked List

DATE: 22.11.2025

AIM:
To write a program that detects a cycle in a linked list and returns the node where the cycle begins. If there is no cycle, the program should return null without modifying the linked list.

###Algorithm


Create a singly linked list by inserting nodes containing integer values.
Use two pointers, slow and fast; move slow one step and fast two steps through the list.
If slow and fast meet, a cycle exists; if fast becomes null, return null since no cycle is present.
Reset slow to the head and move both slow and fast one step at a time until they meet again.
Return the node where they meet, which is the starting point of the cycle.

```

## Program:
```

public class DetectCycle {

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

    // Detect cycle and return the starting node
    public Node detectCycle(Node head) {
        if (head == null) return null;

        Node slow = head;
        Node fast = head;

        // Detect meeting point
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;

            if (slow == fast) {  // Cycle found
                break;
            }
        }

        // No cycle
        if (fast == null || fast.next == null) {
            return null;
        }

        // Find cycle start
        slow = head;
        while (slow != fast) {
            slow = slow.next;
            fast = fast.next;
        }

        return slow; // Starting node of cycle
    }

    // Main
    public static void main(String[] args) {
        DetectCycle list = new DetectCycle();

        // Create list: 10 -> 20 -> 30 -> 40 -> 50
        list.insert(10);
        list.insert(20);
        list.insert(30);
        list.insert(40);
        list.insert(50);

        // Create a cycle manually (50 → 30)
        list.head.next.next.next.next.next = list.head.next.next;

        Node cycleStart = list.detectCycle(list.head);

        if (cycleStart != null) {
            System.out.println("Cycle starts at node with value: " + cycleStart.data);
        } else {
            System.out.println("No cycle detected.");
        }
    }
}

```

## Output:

<img width="1386" height="480" alt="image" src="https://github.com/user-attachments/assets/5bcbacb4-49a2-443e-a04e-cd0aa7e0502f" />


## Result:
Thus, the code to count the number of elements present in the deque is implemented successfully.
