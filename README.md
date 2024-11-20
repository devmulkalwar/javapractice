# 1. Write a Java program that throws an exception and catch it using a try-catch block.
```java
public class ExceptionExample {
    public void throwException() {
        throw new RuntimeException("This is a custom exception");
    }
    public static void main(String[] args) {
        ExceptionExample example = new ExceptionExample();
        try {
            example.throwException();
        } catch (RuntimeException e) {
            System.out.println("Caught exception: " + e.getMessage());
        }
    }
}
```
# 2. Write a Java program to create a method that takes an integer as a parameter and throws an exception if the number is odd.
```java
public class OddNumberException extends Exception {
    public OddNumberException(String message) {
        super(message);
    }
}
public class OddChecker {
    public void checkEvenNumber(int number) throws OddNumberException {
        if (number % 2 != 0) {
            throw new OddNumberException("Number is odd");
        }
        System.out.println("Number is even");
    }
    public static void main(String[] args) {
        OddChecker checker = new OddChecker();
        try {
            checker.checkEvenNumber(5);
        } catch (OddNumberException e) {
            System.out.println("Caught exception: " + e.getMessage());
        }
    }
}
```
# 3. Write a Java program to create a method that reads a file and throws an exception if the file is not found.
```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;
public class FileReader {
    public void readFile(String fileName) throws FileNotFoundException {
        File file = new File(fileName);
        Scanner scanner = new Scanner(file);
        System.out.println("File contents:");
        while (scanner.hasNextLine()) {
            System.out.println(scanner.nextLine());
        }
        scanner.close();
    }
    public static void main(String[] args) {
        FileReader fileReader = new FileReader();
        try {
            fileReader.readFile("nonexistent.txt");
        } catch (FileNotFoundException e) {
            System.out.println("Caught exception: " + e.getMessage());
        }
    }
}
```
# 4. Write a Java program that reads a list of numbers from a file and throws an exception if any of the numbers are positive.
```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class NegativeNumberChecker {
    public void checkNumbers(String fileName) throws Exception {
        File file = new File(fileName);
        Scanner scanner = new Scanner(file);
        while (scanner.hasNextInt()) {
            int number = scanner.nextInt();
            if (number > 0) {
                scanner.close();
                throw new Exception("Positive number found: " + number);
            }
        }
        System.out.println("All numbers are non-positive.");
        scanner.close();
    }
    public static void main(String[] args) {
        NegativeNumberChecker checker = new NegativeNumberChecker();
        try {
            checker.checkNumbers("numbers.txt");
        } catch (Exception e) {
            System.out.println("Caught exception: " + e.getMessage());
        }
    }
}
```
#5. Write a Java program that reads a file and throws an exception if the file is empty.
```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class EmptyFileChecker {
    public void checkFile(String fileName) throws Exception {
        File file = new File(fileName);
        Scanner scanner = new Scanner(file);
        if (!scanner.hasNext()) {
            scanner.close();
            throw new Exception("File is empty");
        }
        System.out.println("File is not empty.");
        scanner.close();
    }
    public static void main(String[] args) {
        EmptyFileChecker checker = new EmptyFileChecker();
        try {
            checker.checkFile("emptyfile.txt");
        } catch (Exception e) {
            System.out.println("Caught exception: " + e.getMessage());
        }
    }
}
```
#6. Write a Java program that reads a list of integers from the user and throws an exception if any numbers are duplicates.
```java
import java.util.HashSet;
import java.util.Scanner;
import java.util.Set;

public class DuplicateNumberChecker {
    public void checkDuplicates(int[] numbers) throws Exception {
        Set<Integer> uniqueNumbers = new HashSet<>();
        for (int number : numbers) {
            if (!uniqueNumbers.add(number)) {
                throw new Exception("Duplicate number found: " + number);
            }
        }
        System.out.println("No duplicates found.");
    }
    public static void main(String[] args) {
        DuplicateNumberChecker checker = new DuplicateNumberChecker();
        Scanner scanner = new Scanner(System.in);
        System.out.println("Enter numbers separated by space:");
        String[] input = scanner.nextLine().split(" ");
        int[] numbers = new int[input.length];
        for (int i = 0; i < input.length; i++) {
            numbers[i] = Integer.parseInt(input[i]);
        }
        try {
            checker.checkDuplicates(numbers);
        } catch (Exception e) {
            System.out.println("Caught exception: " + e.getMessage());
        }
    }
}
```
#7. Write a Java program to create a method that takes a string as input and throws an exception if the string does not contain vowels.
```java
public class VowelChecker {
    public void checkVowels(String input) throws Exception {
        if (!input.matches(".*[aeiouAEIOU].*")) {
            throw new Exception("String does not contain vowels");
        }
        System.out.println("String contains vowels.");
    }
    public static void main(String[] args) {
        VowelChecker checker = new VowelChecker();
        String input = "crypt";
        try {
            checker.checkVowels(input);
        } catch (Exception e) {
            System.out.println("Caught exception: " + e.getMessage());
        }
    }
}
```


