# Part1:
I chose ArrayExamples.java from lab 4 

Failure including input 
```
public class ArrayExamplesTest {

    @Test
    public void testReverseInPlace_Failure() {
        int[] arr = {1, 2, 3, 4, 5};
        ArrayExamples.reverseInPlace(arr);
        assertArrayEquals(new int[]{5, 4, 3, 2, 1}, arr);
    }
}
```

input no failture 
```
public class ArrayExamplesTest {

    @Test
    public void testReverseInPlace_NoFailure() {
        int[] arr = {1, 2, 3};
        ArrayExamples.reverseInPlace(arr);
        assertArrayEquals(new int[]{3, 2, 1}, arr);
    }
}
```

Symptom 

  Bug:
  ```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
        arr[i] = arr[arr.length - i - 1];
    }
}

  ```

  Fix:
  ```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length / 2; i++) {
        int temp = arr[i];
        arr[i] = arr[arr.length - i - 1];
        arr[arr.length - i - 1] = temp;
    }
}
  ```
In the orginal code is pverwirting the elements so in the fix code correctly reversing the elements for the array. Moreover, in the original code the results for all the elements in the array has the same elements. 
In the fixed code correctly reversal of the array. 



# Part2:
For part 2 I want to focus on `grep`
4 interesting command for `grep` which is `-r`,`-i`,`-n`,and `-v`
2 example for `-r`
```
grep -r "pattern" ./technical
```
Explanation for Output:
This command searches for the pattern "pattern" recursively within the ./technical directory.
The search will include all files in the ./technical directory and its subdirectories.
```
grep --recursive "function()" ./technical
```
Explanation for Output: 
This command recursively searches for the pattern "function()" within the ./technical directory.
It will search through all files and subdirectories under ./technical.

-r (Recursive Search)
The -r option allows grep to recursively search directories for a specified pattern. This is particularly useful when you want to search through all files within a directory and its subdirectories.

2 example for `-i`
```
grep -i "success" ./technical/file.txt
```
Explanation for Output:
This command searches for the pattern "success" in a case-insensitive manner within the file.txt located in the ./technical directory.
```
grep --ignore-case "Error" ./technical/file.txt
```
Explanation for Output: 
This command performs a case-insensitive search for the pattern "Error" within the file.txt located in the ./technical directory.

The -i option instructs grep to perform a case-insensitive search, ignoring the case of letters while matching patterns.

2 example for `-n`
```
grep -n "warning" ./technical/file.txt
```
Explanation for Output:
This command searches for the pattern "warning" within the file.txt located in the ./technical directory.
It prints each matching line along with its line number.
```
grep --line-number "example" ./technical/file.txt
```
Explanation for Output:
his command searches for the pattern "example" within the file.txt located in the ./technical directory.

The -n option tells grep to print the line numbers along with the matching lines.
Reference: Provided by ChatGPT
The original output was:
1. -r (Recursive Search)
The -r option enables grep to perform a recursive search through directories for a specified pattern. This is particularly handy when you need to search through multiple files within a directory and its subdirectories.

2. -i (Case-Insensitive Search)
The -i option directs grep to perform a case-insensitive search, disregarding the case of letters when matching patterns.

3. -n (Print Line Numbers)
The -n option instructs grep to display the line numbers alongside the matching lines.



