Flatten an Array

# Flatten an Array
Write a `flattenArray()` method that takes in a 2-dimensional array, flattens it into a 1-dimensional array, and returns it. You can assume that you will only be given one or two-dimensional arrays

For example, calling `flattenArray()` on `[[1, 2], [3, 4, 5])` should return `[1, 2, 3, 4, 5]`.

This challenge was reported to have been asked at interviews with Facebook, as well as right here at Codecademy! If you’ve covered the material in [Pass the Technical Interview with Java](https://www.codecademy.com/learn/paths/pass-the-technical-interview-with-java) or an equivalent, you should be able to solve this challenge. If you have trouble, try refreshing your knowledge there first.

---

```Java
import java.util.*;
import java.lang.*;

public class Flatten_an_Array {

    public static int[] flattenArray(int[][] input) {
        int len = input.length;
        int totalelements = 0;
        for (int l = 0; l < len; l++) {
            totalelements += input[l].length;
        }
        int[] output = new int[totalelements];
        int k = 0;
        for (int i = 0; i < len; i++) {
            for (int j = 0; j < input[i].length; j++) {
                output[k] = input[i][j];
                k++;
            }
        }
        return output;
    }

    public static void main(String[] args) {
        int[][] arr = new int[][]{{1, 2}, {3, 4, 5}};
        int[] answer = flattenArray(arr);
        for (int i = 0; i < answer.length; i++) {
            System.out.println(answer[i]);
        }
    }

}

```