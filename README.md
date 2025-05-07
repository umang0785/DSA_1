# DSA_1
project of DSA

#include <stdio.h>
#include <stdlib.h>
#include <time.h>
void search(int arr[], int size, int key) 
{
    for (int i = 0; i < size; i++) {
        if (arr[i] == key) {
            printf("Element %d found at index %d\n", key, i);
            return;
        }
    }
    printf("Element not found\n");
}
int main(){
    const int size = 5;
    int arr[size];
    int key;
    srand(time(NULL));
    clock_t start_clock = clock();
    time_t start = time(NULL);
    printf("Generated Array:\n");
    for (int i = 0; i < size; i++) {
        arr[i] = rand() % 1000 + 1;
        printf("[%d] = %d\n", i, arr[i]);
    }
    key = arr[rand() % size];
    printf("Randomly Selected Key to Search: %d\n", key);
    search(arr, size, key);
    clock_t end_clock = clock();
    time_t end = time(NULL);
    printf("\nTiming Info:\n");
    printf("Start Time (Epoch): %s", ctime(&start));
    printf("End Time (Epoch):   %s", ctime(&end));
    printf("CPU Clock Time Used: %.6f seconds\n", ((double)(end_clock - start_clock)) / CLOCKS_PER_SEC);
    printf("Wall Clock Time Used: %.2f seconds\n", difftime(end, start));
    return 0;
}
