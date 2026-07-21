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


Problem 2
A library issues books to students and records each book's ID every time it is borrowed. At the
end of the month, the librarian wants to find all books that were borrowed more than once, as
those need priority restocking. Given the borrowing log, print all such book IDs.
Describe the approach you used. How many times does your solution scan the data? If the
library had 100,000 borrow records, would your approach still be practical? Can you think of a
way that requires fewer passes?

#code
#include <iostream>
using namespace std;

int main(){
    int n;
    cout << "Enter number of borrow records: ";
    cin >> n;

    int arr[100];

    cout << "Enter Book IDs:";
    for (int i = 0; i < n; i++) {
        cin >> arr[i];
    }

    cout << "Books borrowed more than once:";

    for (int i = 0; i < n; i++) {
        int count = 0;
        for (int j = 0; j < n; j++) {
            if (arr[i] == arr[j]) {
                count++;
            }
        }
        bool first = true;
        for (int k = 0; k < i; k++) {
            if (arr[i] == arr[k]) {
                first = false;
                break;
            }
        }

        if (count > 1 && first) {
            cout << arr[i] << " ";
        }
    }

    return 0;
}
#error faced
Array out of bounds – if n > 100.
Invalid array size – if n <= 0.
Invalid input – if the user enters characters instead of integers.
No output shown – if no Book ID is repeated (not an error, but a possible case).
Slow execution – for large n because the program uses nested loops (O(n²))

Problem 3
A school newspaper editor wants to highlight the most impressive word from a submitted article
on the front page. The word is chosen simply by length — the longest one wins. Given a
sentence, print the winning word and how many letters it has.
Describe the approach you used. What does your solution do when two words have the same
length? Is that behavior intentional, and can you think of a way to handle it explicitly?

#code
#include <iostream>
#include <string>
using namespace std;

int main() {
    int n;
    string word, longest = "";

    cout << "Enter number of words: ";
    cin >> n;

    cout << "Enter words:";

    for (int i = 0; i < n; i++) {
        cin >> word;

        if (word.length() > longest.length()) {
            longest = word;
        }
    }

    cout << "Longest word: " << longest << endl;
    cout << "Length: " << longest.length();

    return 0;
}

#error faced
No longest word → If n = 0, longest remains empty and its length is 0.
