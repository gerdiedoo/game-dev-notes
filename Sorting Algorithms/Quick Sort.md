```
#include <iostream>

using std::string;
using std::cin;
using std::cout;
using std::endl;

void swap(int& a, int& b) {
    int temp = a;
    a = b;
    b = temp;
}

int partition(int arr[], int start, int end){
    int pivot = arr[end]; // get the last element of the array as a pivot
    int i = start;
    for(int j = start;j<=end-1;j++){
        if(arr[j]<pivot){
            swap(arr[i], arr[j]);
            i++;
        }
    }
    swap(arr[i], arr[end]);
    return i;
}

void sort(int arr[], int start, int end){
    if(start < end){
        int pivot = partition(arr, start, end);
        sort(arr, start, pivot -1);
        sort(arr, pivot+1, end);
    }
}

int main(){
    int arr[] = {9, 8, 7, 6, 5, 4, 3, 2, 1,1,2,3,4,5,6,7,8,9};
    int n = sizeof(arr) / sizeof(arr[0]);
    for(int i = 0;i< n;i++){
        cout << arr[i]<< " ";
    }
    cout << endl;
    sort(arr, 0, n-1);
    for(int i=0;i<n;i++){
        cout << arr[i] << " ";
    }
    cout << endl;
    return 0;
}
```

