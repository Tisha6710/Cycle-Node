# Cycle-Node
package LinkedList;

public class linked {
    public static class Node {
        int data;
        Node next;
        Node(int data) {
            this.data = data;
        }
    }

    public boolean LinkedList(Node head) {
        if (head == null || head.next == null) return false;

        Node slow = head;
        Node fast = head;

        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            if (slow == fast) return true;
        }

        return false;
    }

    public static void main(String[] args) {
        Node head = new Node(1);
        head.next = new Node(2);
        head.next.next = new Node(3);
        head.next.next.next = head.next;  // cycle

        linked obj = new linked();  // ✅ Correct class name
        System.out.println("Cycle exists? " + obj.LinkedList(head)); // Output: true
    }
}
