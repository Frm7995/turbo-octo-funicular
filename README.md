# turbo-octo-funicular
Ffff
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None


class link:

    def __init__(self):
        self.head = None

    def addfirst(self, new_data):
        new_Node = Node(new_data)
        new_Node.next = self.head
        self.head = new_Node

    def addlast(self, new_data):
        new_Node = Node(new_data)
        if self.head is Node:
            self.head = new_Node
            return
        tmp_head = self.head
        while (tmp_head.next):
            tmp_head = tmp_head.next
        tmp_head.next = new_Node

    def addinPosition(self, prev, new_Node):
        if prev is Node:
            raise Exception('Error')

        new_Node = Node(new_Node)
        new_Node.next = prev.next
        prev.next = new_Node

    def removeInPosition(self, data):
        if self.head is None:
            return 'link list is empty'
        tmp_head = self.head
        prev = None
        while True:
            if tmp_head.data == data:
                break
            else:
                if tmp_head.next is None:
                    return 'not in linklist'
                else:
                    prev = tmp_head
                    tmp_head = tmp_head.next
        if prev is None:
            self.head = tmp_head.next
        else:
            prev.next = tmp_head.next
        pass

    def size(self):
        size = 0
        if self.head is None:
            return 'link list is empty'
        tmp_head = self.head
        while tmp_head:
            size += 1
            tmp_head = tmp_head.next
        return f'siza of the list is {size}'

    # def isEmpty(self, linklist: link):
    #     if linklist is Node:
    #         print("yes ,linklist is null")
    #     else:
    #         print("no")
    def removeFirst(self):
        if self.head is None:
            return 'linlist is empty'
        else:
            self.head=self.head.next

    def removeLast(self):
        if self.head is None:
            return 'linlist is empty'
        tmp_head=self.head
        while tmp_head.next.next is not None:
            tmp_head=tmp_head.next
        tmp_head.next=None

    def isEmpty(self):
        if self.head:
            return ('No')
        else:
            return ('Yes')

    def search(self, valeu):
        if self.head is None:
            return 'linklist is empty'
        tmp_head = self.head
        while tmp_head:
            if tmp_head == valeu:
                return 'Yes find it'
            tmp_head = tmp_head.next
        return "no, not found "
    def Print(self):
        if self.head is None:
            return 'link list is empty'
        tmp_head = self.head
        lst=[]
        while (tmp_head):
            lst.append(tmp_head)
            tmp_head = tmp_head.next
        return lst

# Testing

LL=link()
node1=Node(1)
node2=Node(17)
node3=Node('Amir')
node4=Node(2)

print(LL.isEmpty())

LL.addfirst(node1)
LL.addlast(node2)

print(LL.isEmpty())
