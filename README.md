# C Programming – String Functions Lab Assignment


---

## Program 1: Count the Number of Vowels

**Question:** Write a program to read a string and count the number of vowels using a separate function.

### Code

```c
#include <stdio.h>

int countVowels(char str[]) {
    int count = 0;
    for (int i = 0; str[i] != '\0'; i++) {
        char c = str[i];
        if (c=='a'||c=='e'||c=='i'||c=='o'||c=='u'||
            c=='A'||c=='E'||c=='I'||c=='O'||c=='U')
            count++;
    }
    return count;
}

int main() {
    char str[] = "Hello World";
    printf("String: %s\n", str);
    printf("Number of vowels: %d\n", countVowels(str));
    return 0;
}
```

### Output

```
String: Hello World
Number of vowels: 3
```

---

## Program 2: Reverse a String

**Question:** Write a function to reverse a string without using library functions like `strrev()`.

### Code

```c
#include <stdio.h>

void reverseString(char str[]) {
    int len = 0;
    while (str[len] != '\0') len++;
    for (int i = 0; i < len / 2; i++) {
        char temp = str[i];
        str[i] = str[len - 1 - i];
        str[len - 1 - i] = temp;
    }
}

int main() {
    char str[] = "Hello World";
    printf("Original String: %s\n", str);
    reverseString(str);
    printf("Reversed String: %s\n", str);
    return 0;
}
```

### Output

```
Original String: Hello World
Reversed String: dlroW olleH
```

---

## Program 3: Palindrome Check

**Question:** Write a program to check whether a given string is palindrome or not using functions.

### Code

```c
#include <stdio.h>

int isPalindrome(char str[]) {
    int len = 0;
    while (str[len] != '\0') len++;
    for (int i = 0; i < len / 2; i++) {
        if (str[i] != str[len - 1 - i])
            return 0;
    }
    return 1;
}

int main() {
    char str1[] = "madam";
    char str2[] = "hello";
    printf("String: %s -> %s\n", str1,
        isPalindrome(str1) ? "Palindrome" : "Not a Palindrome");
    printf("String: %s -> %s\n", str2,
        isPalindrome(str2) ? "Palindrome" : "Not a Palindrome");
    return 0;
}
```

### Output

```
String: madam -> Palindrome
String: hello -> Not a Palindrome
```

---

## Program 4: Calculate String Length Manually

**Question:** Write a function to calculate the length of a string manually.

### Code

```c
#include <stdio.h>

int stringLength(char str[]) {
    int len = 0;
    while (str[len] != '\0') len++;
    return len;
}

int main() {
    char str[] = "Hello World";
    printf("String: %s\n", str);
    printf("Length: %d\n", stringLength(str));
    return 0;
}
```

### Output

```
String: Hello World
Length: 11
```

---

## Program 5: Count the Number of Words

**Question:** Write a function to count the number of words in a sentence.

### Code

```c
#include <stdio.h>

int countWords(char str[]) {
    int count = 0, inWord = 0;
    for (int i = 0; str[i] != '\0'; i++) {
        if (str[i] != ' ' && str[i] != '\t' && str[i] != '\n') {
            if (!inWord) { count++; inWord = 1; }
        } else {
            inWord = 0;
        }
    }
    return count;
}

int main() {
    char str[] = "Hello World this is C programming";
    printf("Sentence: %s\n", str);
    printf("Number of words: %d\n", countWords(str));
    return 0;
}
```

### Output

```
Sentence: Hello World this is C programming
Number of words: 6
```

---

