Part1:
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



Part2:
For part 2 I want to focus on `grep`
4 interesting command for `grep` which is `-r`,`-i`,`-n`,and `-v`
2 example for `-r`
```
grep -r "pattern" ./technical
```
```
grep --recursive "function()" ./technical
```

2 example for `-i`
```
grep -i "success" ./technical/file.txt
```

```
grep --ignore-case "Error" ./technical/file.txt
```

2 example for `-n`
```
grep -n "warning" ./technical/file.txt
```
```
grep --line-number "example" ./technical/file.txt
```
