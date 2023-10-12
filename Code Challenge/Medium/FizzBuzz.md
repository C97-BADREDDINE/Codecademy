FizzBuzz

# FizzBuzz
Write a `fizzbuzz()` method that takes in a number, `n`, and returns an `ArrayList` of the numbers from 1 to `n`. For multiples of three, use `"Fizz"` instead of the number, and for the multiples of five, use `"Buzz"`. For numbers that are multiples of both three and five, use `"FizzBuzz"` (capitalization matters).

For example, `fizzbuzz(16)` should return `[1, 2, "Fizz", 4, "Buzz", "Fizz", 7, 8, "Fizz", "Buzz", 11, "Fizz", 13, 14, "FizzBuzz", 16]`.

This challenge was reported to have been asked at interviews with many top companies, including Google. If you’ve covered the material in [Pass the Technical Interview with Java](https://www.codecademy.com/learn/paths/pass-the-technical-interview-with-java) or an equivalent, you should be able to solve this challenge. If you have trouble, try refreshing your knowledge there first.

---

```Java
import java.util.*;


public class Fizzbuzz {
    
    
    public static ArrayList fizzbuzz(int n) {

        ArrayList<String> f = new ArrayList<String>();
        for (int i = 1; i < (n+1); i++) {
            if (i % 3 == 0 && i % 5 == 0) {
                f.add("FizzBuzz");
            } else if (i % 3 == 0) {
                f.add("Fizz");
            } else if (i % 5 == 0) {
                f.add("Buzz");
            } else {
                f.add("" + i);
            }
        }
        return f;
    }
    
    public static void main(String[] args) {
        Random rand = new Random();
        int i = rand.nextInt(14, 100);
        System.out.println(""+i);

    }




}

```