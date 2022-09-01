class Node{
    public int data;
    public Node prev;
    public Node next;

    public Node(int data){
        this.data = data;
    }
}

class DoublyLinkedList{
    public Node head;
    public Node tail;

    public DoublyLinkedList(int[] arr){
        if(arr.length <= 0){
            this.head = null;
            this.tail = this.head;
            return;
        }

        this.head = new Node(arr[0]);
        Node currentNode = this.head;
        for(int i=1; i < arr.length; i++){
            currentNode.next = new Node(arr[i]);
            currentNode.next.prev = currentNode;
            currentNode = currentNode.next;
        }
        this.tail = currentNode;
    }

    public Integer peekFront(){
        if(this.head == null) return null;
        return this.head.data;
    }

    public Integer peekBack(){
        if(this.tail == null) return this.peekFront();
        return this.tail.data;

    }

    public Node at(int index){
        Node iterator = this.head;
        for(int i=0; i < index; i++){
            iterator = iterator.next;
            if(iterator == null) return null;
        }
        return iterator;
    }

    public void enqueueFront(int data){
        if(this.head == null){
            this.head = new Node(data);
            this.tail = this.head;
        }else{
            Node node = new Node(data);
            this.head.prev = node;
            node.next = this.head;
            this.head = node;
        }
    }

    public void enqueueBack(int data){
        if(this.head == null){
            this.head = new Node(data);
            this.tail = this.head;
        }
        else{
            Node node = new Node(data);
            this.tail.next = node;
            node.prev = this.tail;
            this.tail = node;
        }
    }

    public void addNextNode(Node node, Node newNode){
        Node tempNode = node.next;
        node.next = newNode;
        newNode.next = tempNode;
        newNode.prev = node;

        if(node == this.tail) this.tail = newNode;
        else tempNode.prev = newNode;
    }

    public Integer dequeueFront(){
        if(this.head == null) return null;

        Node temp = this.head;
        this.head = this.head.next;
        if(this.head != null) this.head.prev = null;
        else this.tail = null;
        return temp.data;
    }

    public Integer dequeueBack(){
        if(this.tail == null) return null;

        Node temp = this.tail;
        this.tail = this.tail.prev;

        if(this.tail != null) this.tail.next = null;
        else this.head = null;
        return temp.data;
    }

    public void deleteNode(Node node){
        if(node == this.tail) this.dequeueBack();
        else if(node == this.head) this.dequeueFront();
        else {
            node.prev.next = node.next;
            node.next.prev = node.prev;
        }
    }

    public void reverse(){
        Node reverse = this.tail;
        Node iterator = this.tail.prev;

        Node currentNode = reverse;
        while(iterator != null){
            currentNode.next = iterator;

            iterator = iterator.prev;
            if(iterator != null) iterator.next = null;

            currentNode.next.prev = currentNode;
            currentNode = currentNode.next;

        }
        this.tail = currentNode;
        this.head = reverse;
        this.head.prev = null;
    }

    public void printInReverse(){
        String str = "";
        Node iterator = this.tail;
        while(iterator != null){
            str += iterator.data + " ";
            iterator = iterator.prev;
        }
        System.out.println("[" + str + "]");
    }

    public void printList(){
        Node iterator = this.head;
        String str = "";
        while(iterator != null){
            str += iterator.data + " ";
            iterator = iterator.next;
        }
        System.out.println("[" + str + "]");
    }
}
