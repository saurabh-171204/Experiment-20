# Experiment-20
## AIM 
To study sorting algorithm and its tyes(selection , insertion and bubble sort) in C++.

## Sorting Algorithm :
A sorting algorithm is a method for arranging elements of a list or array in a particular order, usually in ascending or descending order. The purpose of sorting is to organize data so that it can be searched and processed efficiently. Common examples of sorting algorithms include Selection Sort, Insertion Sort, Bubble Sort .

## Types :
Selection Sort : Selection Sort is an in-place comparison sorting algorithm. It divides the list into two parts: the sorted part at the left end and the unsorted part at the right end. The algorithm repeatedly selects the smallest (or largest, depending on the order) element from the unsorted part and swaps it with the first unsorted element.

Insertion Sort : Insertion Sort is a simple comparison-based algorithm. It builds the final sorted array one item at a time, by comparing each new element to the ones before it and inserting it into the correct position.

Bubble Sort : Bubble Sort is a simple comparison-based algorithm where adjacent elements are compared, and if they are in the wrong order, they are swapped. This process repeats until no more swaps are needed, meaning the array is sorted.
## Code and Output
```
// Sorting Algorithm -> used to rearrange a given array or list of elements according to a comparison operator on the element 
// the comparison operator is used to decide the new order of elements in the respective data structure 

// selection sort

// Name --> SAURABH BIHANI
// PRN --> 23070123166

#include<iostream>
using namespace std;

void swap(int *a,int *b){
    int temp;
    temp=*a;
    *a=*b;
    *b=temp;
}

void s_sort(int* a, int elements){
    for (int i = 0; i < elements - 1; i++) {
        int min_idx = i;  // Assume the minimum element is the first unsorted element
        for (int j = i + 1; j < elements; j++) {
            if (a[j] < a[min_idx]) {  // Find the minimum element in the unsorted part
                min_idx = j;
            }
        }
        // Swap the found minimum element with the first unsorted element
        if (min_idx != i) {
            swap(&a[i], &a[min_idx]);
        }
    }
}

int main(){
    int no_el;
    cout << "How many elements in your array? " << endl;
    cin >> no_el;
    int arr[no_el];  // Array declaration
    cout << "Enter " << no_el << " elements: " << endl;
    for(int i = 0; i < no_el; i++) {
        cin >> arr[i];
    }
    
    s_sort(arr, no_el);  // Call sorting function

    cout << "Sorted Array: ";
    for(int i = 0; i < no_el; i++) {
        cout << arr[i] << " ";  // Corrected the condition in this loop
    }
    cout << endl;

    return 0;
}
```
![374519747-626f0bed-5744-4ea0-ab05-66b653337a55](https://github.com/user-attachments/assets/afbfec1d-b33b-4fd6-80ca-36bf02ff420b)

```
// Insertion Sort 

// Name --> SAURABH BIHANI
// PRN --> 23070123166

#include <iostream>
using namespace std;

void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;

        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
}

int main() {
    int arr[] = {64, 25, 12, 22, 11};
    int n = sizeof(arr) / sizeof(arr[0]);

    cout << "Original array: ";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }

    insertionSort(arr, n);

    cout << "\nSorted array: ";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }

    return 0;
}
```
![374520264-b7d450a5-21db-431b-9c79-fca13cee623c](https://github.com/user-attachments/assets/1b5c4a8e-8648-422c-9b66-1f0cbd33498e)

```
// Bubble Sort 

// Name --> SAURABH BIHANI
// PRN --> 23070123166

#include<iostream>
using namespace std;

void swap(int* a,int* b){
    int temp;
    temp=*a;
    *a=*b;
    *b=temp;
}
int main(){
    int elements;
    cout<<"How many elements in the array? :";
    cin>>elements;
    int array[elements];
    cout<<"Enter elements:";
    for(int i=0;i<elements;i++){
        cin>>array[i];
    }
    for(int i=0;i<elements;i++){
        cout<<array[i]<<" ";
    }
    int n=0;
    while(n!=elements){
        for(int i=0;i<elements-n;i++){
            if(array[i]>array[i+1]){
                swap(&array[i],&array[i+1]);
            }
        }
        n++;
    }
    cout<<"\nSorted array is:"<<endl;
    for(int i=0;i<elements;i++){
        cout<<array[i]<<" ";
    }
    return 0;
}
```
![374521073-8d6fedc3-74e3-4632-b9e2-77d7eef17b10](https://github.com/user-attachments/assets/71d9ab7e-5ef8-451a-86fa-8c35b1aa7617)

