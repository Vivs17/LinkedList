# LinkedList
public class Node {

private int data; 
private Node next; 

public Node(int d,Node n)
{
    data=d;
    next=n;
}

public void setNext(Node n)
{
    next=n;
}

public void setData(int d)
{
    data=d;
}
public Node getNext()
{
    return next;
}

public int getData()
{
    return data;
}
private static Node firstNode; 
private static Node lastNode=null; 

public static void display() //displays all the data in nodes
{
    Node n=firstNode;
    while(n!=null) 
    {
        System.out.print(n.getData()+",  ");
        n=n.getNext(); 
    }
}

public static void create(int d) //inserts the node into the list
{
    Node n =new Node(d, null);
    if(lastNode!=null)
    {
        lastNode.setNext(n);
        lastNode=n;
    }
    else 
    {
        firstNode=n;
        lastNode=n;
    }
}


 public static void removeLast(){
        if (firstNode == null || firstNode.next == null){
            firstNode = null;
            return;
        }
        Node current = firstNode;
        Node tmphead = current;
        while(current.next.next != null){
            current = current.next;
        }
        current.next = null;
        firstNode = tmphead ;
    }


 public static void removeFirst(){
     if(firstNode!=null)
     {
        firstNode= firstNode.next;
     }
    }

public static void main(String[] args) {

    create(10);
    create(20);
    create(30);
    create(40);
    create(50);
    create(60);
    display();
    System.out.println();
    removeLast();
    display();
    System.out.println();
    removeFirst();
    display();
}
}
