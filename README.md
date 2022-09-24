# linked-list-insert-any-pos
import java.util.*;
import java.lang.*;
import java.io.*;

public class Main
{
	public static void main (String[] args) throws java.lang.Exception
	{
                Scanner sc=new Scanner(System.in);
                int n=sc.nextInt();
                check p=new check();
                for(int i=0;i<n;i++){
                        p.add(sc.nextInt());
                }
                int pos=sc.nextInt();
                int key=sc.nextInt();
                p.addpoint(pos,key);
                p.print();
		
	}
}
class check{
        Node head;
        Node temp;
        void add(int data){
                Node newnode=new Node(data);
                if(head==null){
                        head=newnode;
                        temp=newnode;
                        return;
                }
                temp.next=newnode;
                temp=newnode;
        }
        void addpoint(int pos,int key){
                
                 Node temp=head;
                if(pos<1)
                        
                        System.out.println("invalid postion");
                               
                if(pos==1){
                         Node newnode=new Node(key);
                        newnode.next=temp;
                        head=newnode;
                }
               else{
                 Node newnode=new Node(key);
               
               
                for(int i=1;i<pos-1;i++){
                        temp=temp.next;
                }
                newnode.next=temp.next;
                temp.next=newnode;
        }
        }
        void print(){
                Node temp=head;
                while(temp!=null){
                        System.out.print(temp.data+" ");
                        temp=temp.next;
                }
                
        }
}
class Node{
        int data;
        Node next;
        Node(int data){
                this.data=data;
                this.next=null;
        }
}
