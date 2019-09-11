# 单项链表数据结构

``` javascript
class Node {
    constructor(value, next){
        this.value = value;
        this.next = null;
    }
}
class LinkList {
    constructor(){
        this.head = null;
    }
    find(value){
        let curNode = this.head;
        while(curNode.value != value){
            curNode = curNode.next;
        }
        return curNode;
    }
    findPrev(value){
        let curNode = this.head;
        while(curNode.value != null && curNode.next.value != value){
            curNode = curNode.next;
        }
        return curNode;
    }
    insert(newValue, value){
        const newNode = new Node(newValue);
        const curNode = this.find(value);
        newNode.next = curNode.next;
        curNode.next = newNode;
    }
    remove(value){
        const preNode = this.findPrev(value);
        const curNode = preNode.next;
        preNode.next = preNode.next.next;
        return curNode;
    }

}
```