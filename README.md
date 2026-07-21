# 25dce103-batchB

#DSApractical 1-left rotation on array

#Definition
Problem 1
A bakery prepares n items every morning and places them in a display row. At the end of each
hour, the leftmost item is moved to the rightmost position to make room for fresh stock at the
front. Given the initial row and the number of hours h, print the final display order.
Describe the approach you used. How does it behave when h is very large, say 10 million? Is
there a way to get the correct result without performing the operation h times?
#Code
#include<iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number: ";
    cin >> n;

    int arr[100];
    cout << "Enter array elements:\n";
    for(int i = 0; i < n; i++) {
        cin >> arr[i];
    }

    int h;
    cout << "Enter elements: ";
    cin >> h;
    h = h % n;

    cout << "Display output: ";

    for(int i = h; i < n; i++) {
        cout << arr[i] << " ";
    }

    for(int i = 0; i < h; i++) {
        cout << arr[i] << " ";
    }

    return 0;
}

#error feced
n = 0 → h % n causes division by zero.
Negative h → Rotation may give incorrect output.
Time Complexity: O(n)
Space Complexity: O(1)
