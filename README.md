# Exception-handling
import java.util.Scanner;

public class ErrorHandlingExample {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        try {
            System.out.print("Enter a number: ");
            int number = scanner.nextInt();

            // Check if the entered number is positive
            if (number < 0) {
                throw new IllegalArgumentException("Entered number must be positive.");
            }

            // Perform some operation with the positive number
            int result = 10 / number;

            System.out.println("Result: " + result);
        } catch (IllegalArgumentException e) {
            System.out.println("Error: " + e.getMessage());
        } catch (ArithmeticException e) {
            System.out.println("Error: Cannot divide by zero.");
        } catch (Exception e) {
            System.out.println("An unexpected error occurred: " + e.getMessage());
        } finally {
            // Close resources or perform cleanup tasks
            System.out.println("Finally block executed.");
            scanner.close();
        }
    }
}
