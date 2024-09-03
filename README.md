# DSA-programs
#linkedist

public class Main{
    public static class Node{
        int data;
        Node next;

        public Node(int data){
            this.data=data;
            this.next=null;
        }
    }
    public void addFirst(int data){
        Node newNode=new Node(data);
        size++;
        if(head==null){
            head=tail=newNode;
        }
        newNode.next=head;
        head=newNode;
    }
    void addLast(int data){
        Node newNode=new Node(data);
        size++;

        if(head==null){
            head=tail=newNode;
        }
        tail.next=newNode;
        tail=newNode;
    }
    public int removeFirst(){
        if(size==0){
            System.out.println("ll is empty");
            return Integer.MIN_VALUE;
        } else if (size==1) {
            int val=head.data;
            head=tail=null;
            return val;
        }
        int val=head.data;
        head=head.next;
        size--;
        return val;

    }
    public int removeLast(){
        int val=head.data;
        if(size==0){
            System.out.println("ll is empty");
            return Integer.MIN_VALUE;
        } else if (size==1) {
            val=head.data;
            head=tail=null;
            size--;

        }
        Node prev=head;
        for(int i =0;i<size-2;i++){
            prev=prev.next;
        }
        prev.next=null;
        tail=prev;
        size--;
        return val;

    }
    ############ **Removing element into linkedList**  ##########################

    class Solution {
    public ListNode removeElements(ListNode head, int val) {
      while(head!=null && head.val==val){
        head=head.next;
      }
      ListNode temp=head;
      while(temp!=null&&temp.next!=null){
            if(temp.next.val==val){
                temp.next=temp.next.next;
            }else{
                temp=temp.next;
            }
      }
      return temp;
    }

}

    void print(){
        Node temp=head;
        while(temp!=null){
            System.out.println(temp.data);
            temp=temp.next;
        }
    }
    void add(int indx,int data) {
        Node newNode=new Node(data);
        int i=0;
        Node temp=head;
        while(i<indx-1){
            temp=temp.next;
            i++;
        }
        newNode.next=temp.next;
        temp.next=newNode;

    }
    // searching the element in the ll
    public int iterSearch(int key){
        int i=0;
        Node temp=head;
        while(temp!=null){
        if(temp.val==key){
        return i;
        }
        temp=temp.next;
        i++;
        }
        return -1;
    
    }
   public void reverse(){
     Node prev=null;
     Node curr=tail=head;
     Node next;
     while(curr !=null){
       next=curr.next;
       curr.next=prev;
       prev=curr;
       curr=next;}
       head=prev;
       }
       
    

    public static Node head;
    public static Node tail;
    public static int size;

    public static void main(String[]args){
        Main ll=new Main();
        ll.addFirst(2);
        ll.addFirst(3);
        ll.addLast(4);
        ll.addLast(5);
        ll.add(4,12);
        ll.removeFirst();
        ll.removeLast();
        ll.print();
        System.out.println(ll.size);

    }
}
