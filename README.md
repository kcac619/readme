

## Problem 1: Array Peak Finder
 
**Title: Array Peak Finder**

**Description:**

In an array of integers, a **peak** is an element that is not smaller than its neighbours. Your task is to find and print the first peak in the array. If no peak exists, print `-1`.

**Problem Statement:**

Given an array `A` of size `N`, find the first peak element. An element `A[i]` is considered a peak if:
- `A[i] >= A[i-1]` (if `i > 0`) and `A[i] >= A[i+1]` (if `i < N-1`)

If the array does not have a peak, return `-1`.

**Input Format:**

- The first line contains a single integer `N` (1 ≤ N ≤ 1000), representing the size of the array.
- The second line contains `N` space-separated integers `A[i]` (1 ≤ A[i] ≤ 10^6), representing the elements of the array.

**Constraints:**

- The array `A` can have duplicate elements.

**Output Format:**

- Print the index of the first peak element in the array (0-based index). If no peak exists, print `-1`.

**Tags:**

- Arrays
- Searching
- Basic Operations

---

**Sample Input 0:**

```
5
1 3 2 4 1
```

**Sample Output 0:**

```
1
```

---

**Sample Input 1:**

```
6
6 5 4 3 2 1
```

**Sample Output 1:**

```
0
```

---

**Sample Input 2:**

```
4
1 2 3 4
```

**Sample Output 2:**

```
3
```

---

**Explanation:**

**Sample Input 0:**

- The array is `[1, 3, 2, 4, 1]`.
- `A[1] = 3` is a peak because it is greater than `A[0]` and `A[2]`.
- The first peak is at index `1`.

**Sample Input 1:**

- The array is `[6, 5, 4, 3, 2, 1]`.
- `A[0] = 6` is a peak because it is greater than `A[1]`.
- The first peak is at index `0`.

**Sample Input 2:**

- The array is `[1, 2, 3, 4]`.
- `A[3] = 4` is a peak because it is greater than `A[2]`.
- The first peak is at index `3`.

---

### Sample Solution Code

Here’s a sample solution for the above problem in various programming languages:

#### Python

```python
def find_first_peak(A):
    N = len(A)
    for i in range(N):
        if (i == 0 or A[i] >= A[i - 1]) and (i == N - 1 or A[i] >= A[i + 1]):
            return i
    return -1

# Reading inputs
N = int(input())
A = list(map(int, input().split()))

# Finding the first peak
result = find_first_peak(A)
print(result)
```

#### Java

```java
import java.util.Scanner;

public class ArrayPeakFinder {
    public static int findFirstPeak(int[] A) {
        int N = A.length;
        for (int i = 0; i < N; i++) {
            if ((i == 0 || A[i] >= A[i - 1]) && (i == N - 1 || A[i] >= A[i + 1])) {
                return i;
            }
        }
        return -1;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();
        int[] A = new int[N];
        for (int i = 0; i < N; i++) {
            A[i] = scanner.nextInt();
        }

        int result = findFirstPeak(A);
        System.out.println(result);
    }
}
```

#### C++

```cpp
#include <iostream>
#include <vector>

using namespace std;

int findFirstPeak(const vector<int>& A) {
    int N = A.size();
    for (int i = 0; i < N; i++) {
        if ((i == 0 || A[i] >= A[i - 1]) && (i == N - 1 || A[i] >= A[i + 1])) {
            return i;
        }
    }
    return -1;
}

int main() {
    int N;
    cin >> N;
    vector<int> A(N);
    for (int i = 0; i < N; i++) {
        cin >> A[i];
    }

    int result = findFirstPeak(A);
    cout << result << endl;

    return 0;
}
```

#### JavaScript

```javascript
function findFirstPeak(A) {
    const N = A.length;
    for (let i = 0; i < N; i++) {
        if ((i === 0 || A[i] >= A[i - 1]) && (i === N - 1 || A[i] >= A[i + 1])) {
            return i;
        }
    }
    return -1;
}

// Reading inputs
const inputLines = require('fs').readFileSync(0, 'utf-8').trim().split('\n');
const N = parseInt(inputLines[0]);
const A = inputLines[1].split(' ').map(Number);

// Finding the first peak
const result = findFirstPeak(A);
console.log(result);
```

#### C#

```csharp
using System;

class ArrayPeakFinder {
    static int FindFirstPeak(int[] A) {
        int N = A.Length;
        for (int i = 0; i < N; i++) {
            if ((i == 0 || A[i] >= A[i - 1]) && (i == N - 1 || A[i] >= A[i + 1])) {
                return i;
            }
        }
        return -1;
    }

    static void Main() {
        int N = int.Parse(Console.ReadLine());
        int[] A = Array.ConvertAll(Console.ReadLine().Split(' '), int.Parse);

        int result = FindFirstPeak(A);
        Console.WriteLine(result);
    }
}
```

#### Go

```go
package main

import (
	"fmt"
)

func findFirstPeak(A []int) int {
	N := len(A)
	for i := 0; i < N; i++ {
		if (i == 0 || A[i] >= A[i-1]) && (i == N-1 || A[i] >= A[i+1]) {
			return i
		}
	}
	return -1
}

func main() {
	var N int
	fmt.Scan(&N)
	A := make([]int, N)
	for i := 0; i < N; i++ {
		fmt.Scan(&A[i])
	}

	result := findFirstPeak(A)
	fmt.Println(result)
}
```

#### Ruby

```ruby
def find_first_peak(a)
    n = a.length
    (0...n).each do |i|
        if (i == 0 || a[i] >= a[i - 1]) && (i == n - 1 || a[i] >= a[i + 1])
            return i
        end
    end
    return -1
end

n = gets.to_i
a = gets.split.map(&:to_i)

result = find_first_peak(a)
puts result
```

---



## Problem 2: String Rotation Check

**Title: String Rotation Check**

**Description:**

Given two strings `s1` and `s2`, check if `s2` is a rotation of `s1`. A string `s2` is considered a rotation of `s1` if `s2` can be obtained by rotating `s1` any number of times. For example, "abcde" is a rotation of "cdeab".

**Problem Statement:**

Write a program that checks if one string is a rotation of another.

**Input Format:**

- The first line contains a single string `s1` (1 ≤ |s1| ≤ 1000), the original string.
- The second line contains a single string `s2` (1 ≤ |s2| ≤ 1000), the string to be checked for rotation.

**Constraints:**

- Both strings have the same length.

**Output Format:**

- Print `True` if `s2` is a rotation of `s1`. Otherwise, print `False`.

**Tags:**

- Strings
- Rotation
- Basic Operations

---

**Sample Input 0:**

```
waterbottle
erbottlewat
```

**Sample Output 0:**

```
True
```

---

**Sample Input 1:**

```
hello
lohel
```

**Sample Output 1:**

```
True
```

---

**Sample Input 2:**

```
abc
def
```

**Sample Output 2:**

```
False
```

---

### Sample Solution Code

#### Python

```python
def is_rotation(s1, s2):
    if len(s1) != len(s2):
        return False
    return s2 in (s1 + s1)

# Reading inputs
s1 = input().strip()
s2 = input().strip()

# Checking for rotation
result = is_rotation(s1, s2)
print(result)
```

#### C++

```cpp
#include <iostream>
#include <string>

using namespace std;

bool isRotation(const string& s1, const string& s2) {
    if (s1.length() != s2.length()) return false;
    string doubled_s1 = s1 + s1;
    return doubled_s1.find(s2) != string::npos;
}

int main() {
    string s1, s2;
    getline(cin, s1);
    getline(cin, s2);

    bool result = isRotation(s1, s2);
    cout << (result ? "True" : "False") << endl;

    return 0;
}
```

#### Java

```java
import java.util.Scanner;

public class StringRotationCheck {
    public static boolean isRotation(String s1, String s2) {
        if (s1.length() != s2.length()) return false;
        String doubledS1 = s1 + s1;
        return doubledS1.contains(s2);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String s1 = scanner.nextLine();
        String s2 = scanner.nextLine();

        boolean result = isRotation(s1, s2);
        System.out.println(result ? "True" : "False");
    }
}
```

---



## Problem 3: Remove Duplicates from Sorted Linked List

**Title: Remove Duplicates from Sorted Linked List**

**Description:**

Given a sorted linked list, write a program to remove all duplicates such that each element appears only once.

**Problem Statement:**

You are given the head of a sorted linked list. Your task is to remove all duplicates from the list so that each element appears only once. Return the head of the modified list.

**Input Format:**

- The first line contains a single integer `N` (1 ≤ N ≤ 1000), representing the number of elements in the linked list.
- The second line contains `N` space-separated integers, representing the elements of the linked list in sorted order.

**Constraints:**

- The linked list is sorted in non-decreasing order.

**Output Format:**

- Print the elements of the modified linked list, each element separated by a space.

**Tags:**

- Linked List
- Removing Duplicates
- Basic Operations

---

**Sample Input 0:**

```
5
1 1 2 3 3
```

**Sample Output 0:**

```
1 2 3
```

---

**Sample Input 1:**

```
7
1 2 2 3 3 4 5
```

**Sample Output 1:**

```
1 2 3 4 5
```

---

**Sample Input 2:**

```
3
1 1 1
```

**Sample Output 2:**

```
1
```

---

### Sample Solution Code

#### Python

```python
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

def remove_duplicates(head):
    current = head
    while current and current.next:
        if current.val == current.next.val:
            current.next = current.next.next
        else:
            current = current.next
    return head

def print_linked_list(head):
    current = head
    while current:
        print(current.val, end=" ")
        current = current.next
    print()

# Reading inputs
N = int(input())
elements = list(map(int, input().split()))

# Creating the linked list
head = ListNode(elements[0])
current = head
for i in range(1, N):
    current.next = ListNode(elements[i])
    current = current.next

# Removing duplicates
head = remove_duplicates(head)

# Printing the result
print_linked_list(head)
```

#### C++

```cpp
#include <iostream>

struct ListNode {
    int val;
    ListNode *next;
    ListNode(int x) : val(x), next(NULL) {}
};

ListNode* removeDuplicates(ListNode* head) {
    ListNode* current = head;
    while (current != NULL && current->next != NULL) {
        if (current->val == current->next->val) {
            ListNode* temp = current->next;
            current->next = current->next->next;
            delete temp;
        } else {
            current = current->next;
        }
    }
    return head;
}

void printLinkedList(ListNode* head) {
    ListNode* current = head;
    while (current != NULL) {
        std::cout << current->val << " ";
        current = current->next;
    }
    std::cout << std::endl;
}

int main() {
    int N;
    std::cin >> N;
    int val;
    std::cin >> val;
    ListNode* head = new ListNode(val);
    ListNode* current = head;
    for (int i = 1; i < N; ++i) {
        std::cin >> val;
        current->next = new ListNode(val);
        current = current->next;
    }

    head = removeDuplicates(head);

    printLinkedList(head);

    // Free memory
    current = head;
    while (current != NULL) {
        ListNode* next = current->next;
        delete current;
        current = next;
    }

    return 0;
}
```

#### Java

```java
import java.util.Scanner;

class ListNode {
    int val;
    ListNode next;
    ListNode(int x) { val = x; }
}

public class RemoveDuplicatesLinkedList {
    public static ListNode removeDuplicates(ListNode head) {
        ListNode current = head;
        while (current != null && current.next != null) {
            if (current.val == current.next.val) {
                current.next = current.next.next;
            } else {
                current = current.next;
            }
        }
        return head;
    }

    public static void printLinkedList(ListNode head) {
        ListNode current = head;
        while (current != null) {
            System.out.print(current.val + " ");
            current = current.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();
        ListNode head = new ListNode(scanner.nextInt());
        ListNode current = head;
        for (int i = 1; i < N; i++) {
            current.next = new ListNode(scanner.nextInt());
            current = current.next;
        }

        head = removeDuplicates(head);

        printLinkedList(head);
    }
}
```

---


---

## Problem 4: Circular Array Rotation

**Title: Circular Array Rotation**

**Description:**

You are given an array of integers and a number `k`. Your task is to rotate the array `k` times to the right in a circular fashion.

**Problem Statement:**

Write a program to perform a circular rotation on an array of integers. In a circular rotation, the last element of the array becomes the first element, and all other elements move one position to the right. Repeat this process `k` times.

**Input Format:**

- The first line contains two integers `N` and `k` (1 ≤ N ≤ 1000, 1 ≤ k ≤ 1000), where `N` is the number of elements in the array and `k` is the number of rotations.
- The second line contains `N` space-separated integers `A[i]` (1 ≤ A[i] ≤ 1000), representing the elements of the array.

**Output Format:**

- Print the elements of the array after `k` rotations, each element separated by a space.

**Tags:**

- Arrays
- Rotations
- Basic Operations

---

**Sample Input 0:**

```
5 2
1 2 3 4 5
```

**Sample Output 0:**

```
4 5 1 2 3
```

---

**Sample Input 1:**

```
4 1
10 20 30 40
```

**Sample Output 1:**

```
40 10 20 30
```

---

**Sample Input 2:**

```
3 3
7 8 9
```

**Sample Output 2:**

```
7 8 9
```

---

### Sample Solution Code

#### Python

```python
def circular_array_rotation(arr, k):
    n = len(arr)
    k = k % n  # Handle rotations larger than array size
    return arr[-k:] + arr[:-k]

# Reading inputs
N, k = map(int, input().split())
arr = list(map(int, input().split()))

# Performing circular array rotation
rotated_arr = circular_array_rotation(arr, k)

# Printing the result
print(*rotated_arr)
```

#### C++

```cpp
#include <iostream>
#include <vector>

using namespace std;

vector<int> circularArrayRotation(const vector<int>& arr, int k) {
    int n = arr.size();
    k = k % n;  // Handle rotations larger than array size
    vector<int> rotatedArr(n);
    for (int i = 0; i < n; ++i) {
        rotatedArr[(i + k) % n] = arr[i];
    }
    return rotatedArr;
}

int main() {
    int N, k;
    cin >> N >> k;
    vector<int> arr(N);
    for (int i = 0; i < N; ++i) {
        cin >> arr[i];
    }

    vector<int> result = circularArrayRotation(arr, k);
    for (int i = 0; i < N; ++i) {
        cout << result[i] << " ";
    }
    cout << endl;

    return 0;
}
```

#### Java

```java
import java.util.Scanner;

public class CircularArrayRotation {
    public static int[] circularArrayRotation(int[] arr, int k) {
        int n = arr.length;
        k = k % n;  // Handle rotations larger than array size
        int[] rotatedArr = new int[n];
        for (int i = 0; i < n; i++) {
            rotatedArr[(i + k) % n] = arr[i];
        }
        return rotatedArr;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();
        int k = scanner.nextInt();
        int[] arr = new int[N];
        for (int i = 0; i < N; i++) {
            arr[i] = scanner.nextInt();
        }

        int[] result = circularArrayRotation(arr, k);
        for (int i = 0; i < N; i++) {
            System.out.print(result[i] + " ");
        }
        System.out.println();
    }
}
```

---

## Problem 5: First Unique Character in a String

**Title: First Unique Character in a String**

**Description:**

You are given a string consisting of lowercase English letters. Your task is to find the first character that does not repeat anywhere in the string.

**Problem Statement:**

Write a program to find the first non-repeating character in a given string and return its index. If all characters are repeating, return `-1`.

**Input Format:**

- A single line containing a string `S` (1 ≤ |S| ≤ 1000), consisting of lowercase English letters.

**Output Format:**

- Print a single integer representing the index of the first unique character. If all characters are repeating, print `-1`.

**Tags:**

- Strings
- Searching
- Basic Operations

---

**Sample Input 0:**

```
abacabad
```

**Sample Output 0:**

```
3
```

---

**Sample Input 1:**

```
aabbcc
```

**Sample Output 1:**

```
-1
```

---

**Sample Input 2:**

```
loveleetcode
```

**Sample Output 2:**

```
2
```

---

### Sample Solution Code

#### Python

```python
def first_unique_char(s):
    char_count = {}
    for char in s:
        char_count[char] = char_count.get(char, 0) + 1
    
    for i, char in enumerate(s):
        if char_count[char] == 1:
            return i
    return -1

# Reading input
s = input().strip()

# Finding the first unique character
result = first_unique_char(s)
print(result)
```

#### C++

```cpp
#include <iostream>
#include <unordered_map>
#include <string>

using namespace std;

int firstUniqueChar(const string& s) {
    unordered_map<char, int> charCount;
    for (char c : s) {
        charCount[c]++;
    }

    for (int i = 0; i < s.length(); ++i) {
        if (charCount[s[i]] == 1) {
            return i;
        }
    }
    return -1;
}

int main() {
    string s;
    cin >> s;

    int result = firstUniqueChar(s);
    cout << result << endl;

    return 0;
}
```

#### Java

```java
import java.util.HashMap;
import java.util.Map;
import java.util.Scanner;

public class FirstUniqueCharacter {
    public static int firstUniqueChar(String s) {
        Map<Character, Integer> charCount = new HashMap<>();
        for (char c : s.toCharArray()) {
            charCount.put(c, charCount.getOrDefault(c, 0) + 1);
        }

        for (int i = 0; i < s.length(); i++) {
            if (charCount.get(s.charAt(i)) == 1) {
                return i;
            }
        }
        return -1;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String s = scanner.nextLine();

        int result = firstUniqueChar(s);
        System.out.println(result);
    }
}
```

---

## Problem 6: Reverse Words in a String

**Title: Reverse Words in a String**

**Description:**

Given a string `S` containing a sentence with words separated by spaces, your task is to reverse the order of words in the string. The string may contain leading or trailing spaces, but the output should not.

**Problem Statement:**

Write a program to reverse the order of words in a given string. The words should be separated by a single space.

**Input Format:**

- A single line containing the string `S` (1 ≤ |S| ≤ 1000), which contains words separated by spaces.

**Output Format:**

- Print the string with the words in reverse order, separated by a single space, with no leading or trailing spaces.

**Tags:**

- Strings
- Basic Operations

---

**Sample Input 0:**

```
hello world this is a test
```

**Sample Output 0:**

```
test a is this world hello
```

---

**Sample Input 1:**

```
  welcome to   coding   
```

**Sample Output 1:**

```
coding to welcome
```

---

**Sample Input 2:**

```
singleword
```

**Sample Output 2:**

```
singleword
```

---

### Sample Solution Code

#### Python

```python
def reverse_words(s):
    words = s.split()
    return ' '.join(reversed(words))

# Reading input
s = input().strip()

# Reversing the words in the string
result = reverse_words(s)
print(result)
```

#### C++

```cpp
#include <iostream>
#include <sstream>
#include <vector>
#include <algorithm>

using namespace std;

string reverseWords(string s) {
    vector<string> words;
    stringstream ss(s);
    string word;
    while (ss >> word) {
        words.push_back(word);
    }
    reverse(words.begin(), words.end());
    string result;
    for (int i = 0; i < words.size(); ++i) {
       

 result += words[i];
        if (i < words.size() - 1) {
            result += " ";
        }
    }
    return result;
}

int main() {
    string s;
    getline(cin, s);

    string result = reverseWords(s);
    cout << result << endl;

    return 0;
}
```

#### Java

```java
import java.util.Scanner;

public class ReverseWordsInString {
    public static String reverseWords(String s) {
        String[] words = s.trim().split("\\s+");
        StringBuilder sb = new StringBuilder();
        for (int i = words.length - 1; i >= 0; i--) {
            sb.append(words[i]);
            if (i > 0) {
                sb.append(" ");
            }
        }
        return sb.toString();
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String s = scanner.nextLine();

        String result = reverseWords(s);
        System.out.println(result);
    }
}
```

---
