# homeworks

#include <stdio.h>
#include <stdlib.h>
#include <stdio.h>

struct Node {
    int data;
    struct Node* next;
};

typedef struct Node Node;

// Yeni düğüm oluşturur
Node* createNode(int data) {
    Node* yeniNode = (Node*)malloc(sizeof(Node));
    yeniNode->data = data;
    yeniNode->next = NULL;
    return yeniNode;
}

// Listenin başına düğüm ekler
Node* prepend(Node* head, int data) {
    Node* yeniNode = createNode(data);
    yeniNode->next = head;
    return newNode;
}

// Listenin sonuna düğüm ekler
Node* append(Node* head, int data) {
    Node* yeniNode = createNode(data);
    if (head == NULL) {
        return yeniNode;
    }
    Node* current = head;
    while (current->next != NULL) {
        current = current->next;
    }
    current->next = newNode;
    return head;
}

// Liste elemanlarını yazdırır
void printList(Node* head) {
    Node* current = head;
    while (current != NULL) {
        printf("%d -> ", current->data);
        current = current->next;
    }
    printf("NULL\n");
}

int main() {
    Node* head = NULL;
    int num;

    printf("Sayilari girin):\n");

    while (1) {
        scanf("%d", &num);
        if (num == -1) {
            break;
        }

        if (num % 2 == 0) {
            head = append(head, num);
        } else {
            head = prepend(head, num);
        }
    }

    printf("Duzenlenmis liste: ");
    printList(head);

    return 0;
}
