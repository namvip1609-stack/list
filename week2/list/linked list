struct SNode {
    int data;
    SNode* next;
    SNode(int val) : data(val), next(nullptr) {}
};

class SinglyLinkedList {
private:
    SNode* head;

public:
    SinglyLinkedList() : head(nullptr) {}

    // 1. Chèn đầu
    void insertHead(int val) {
        SNode* newNode = new SNode(val);
        newNode->next = head;
        head = newNode;
    }

    // 2. Chèn cuối
    void insertTail(int val) {
        SNode* newNode = new SNode(val);
        if (!head) {
            head = newNode;
            return;
        }
        SNode* temp = head;
        while (temp->next) temp = temp->next;
        temp->next = newNode;
    }

    // 3. Chèn vị trí i
    void insertAt(int val, int pos) {
        if (pos == 0) {
            insertHead(val);
            return;
        }
        SNode* temp = head;
        for (int i = 0; temp && i < pos - 1; i++) temp = temp->next;
        if (!temp) return; // Vị trí nằm ngoài phạm vi

        SNode* newNode = new SNode(val);
        newNode->next = temp->next;
        temp->next = newNode;
    }

    // 4. Xóa đầu
    void deleteHead() {
        if (!head) return;
        SNode* temp = head;
        head = head->next;
        delete temp;
    }

    // 5. Xóa cuối
    void deleteTail() {
        if (!head) return;
        if (!head->next) {
            delete head;
            head = nullptr;
            return;
        }
        SNode* temp = head;
        while (temp->next->next) temp = temp->next;
        delete temp->next;
        temp->next = nullptr;
    }

    // 6. Xóa vị trí i
    void deleteAt(int pos) {
        if (!head) return;
        if (pos == 0) {
            deleteHead();
            return;
        }
        SNode* temp = head;
        for (int i = 0; temp && i < pos - 1; i++) temp = temp->next;
        if (!temp || !temp->next) return;

        SNode* nodeToDelete = temp->next;
        temp->next = nodeToDelete->next;
        delete nodeToDelete;
    }

    // 7. Duyệt đầu -> cuối
    void printForward() {
        cout << "[SLL Forward]: ";
        SNode* temp = head;
        while (temp) {
            cout << temp->data << " ";
            temp = temp->next;
        }
        cout << endl;
    }

    // 8. Duyệt cuối -> đầu (Dùng khử đệ quy/Hàm phụ đệ quy)
    void printBackwardHelper(SNode* node) {
        if (!node) return;
        printBackwardHelper(node->next);
        cout << node->data << " ";
    }

    void printBackward() {
        cout << "[SLL Backward]: ";
        printBackwardHelper(head);
        cout << endl;
    }
};
