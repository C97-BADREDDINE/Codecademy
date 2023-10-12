Max Product Finder

# Max Product Finder
Create a `maxProductFinderK()` method that takes in a list of numbers and an integer `k`, and returns the largest product that can be attained from any `k` integers in the list. You may presume that the length of the list of integers is greater than or equal to `k`.

For example, calling `maxProductFinderK()` on `([-8, 6, -7, 3, 2, 1, -9], 2)` should return `72`, and calling `maxProductFinderK()` on `([-8, 6, -7, 3, 2, 1, -9], 3)` should return `432`.

This challenge was reported to have been asked at interviews with Google. If you’ve covered the material in [Pass the Technical Interview with Java](https://www.codecademy.com/learn/paths/pass-the-technical-interview-with-java) or an equivalent, you should be able to solve this challenge. If you have trouble, try refreshing your knowledge with its [Heaps](https://www.codecademy.com/paths/pass-the-technical-interview-with-java/tracks/nonlinear-data-structures-java/modules/heaps-java/lessons/conceptual-heaps/exercises/conceptual-heaps-heapify-down) content.

---

```Java
import java.util.Arrays;
import java.util.ArrayList;
import java.util.List;

public class MaxProductFinder {
  public static void main(String[] args) {
    int[] elements = new int[]{-8, 6, -7, 3, 2, 1, -9};
    int result = maxProductFinderK(elements, 3);
    System.out.println(result);
  }
    public static List<List<Integer>> generateNDigitEvents(int[] elements, int n) {
        List<List<Integer>> result = new ArrayList<>();
        generateNDigitEventsRecursive(elements, n, new ArrayList<>(), result);
        return result;
    }
    private static void generateNDigitEventsRecursive(int[] elements, int n, List<Integer> current, List<List<Integer>> result) {
        if (n == 0) {
            result.add(new ArrayList<>(current));
            return;
        }

        for (int i = 0; i < elements.length; i++) {
            if (!current.contains(elements[i])) {
                current.add(elements[i]);
                generateNDigitEventsRecursive(elements, n - 1, current, result);
                current.remove(current.size() - 1);
            }
        }
    }
  public static int maxProductFinderK(int[] elements, int n) {
    // Write your code here
        List<List<Integer>> result = generateNDigitEvents(elements, n);

        int maxproduct = 0;

        // Print the generated n-digit events
        for (List<Integer> event : result) {
            
            int product = 1;
            for (int f = 0; f < n; f++) {
                product *= event.get(f);
            }
            maxproduct = Math.max(maxproduct, product);
        }
        return maxproduct;
  }
}
```
