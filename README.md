// Online Java Compiler
// Use this editor to write, compile and run your Java code online
import java.util.Scanner;

public class Calculator {

    // Performs addition
    public static double add(double num1, double num2) {
        return num1 + num2;
    }

    // Performs subtraction
    public static double subtract(double num1, double num2) {
        return num1 - num2;
    }

    // Performs multiplication
    public static double multiply(double num1, double num2) {
        return num1 * num2;
    }

    // Performs division with zero check
    public static double divide(double num1, double num2) {
        if (num2 == 0) {
            System.out.println("Oops! Can't divide by zero.");
            return 0;
        }
        return num1 / num2;
    }

    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);
        boolean running = true;

        System.out.println("=== Welcome to Java Console Calculator ===");

        while (running) {
            System.out.println("\nChoose an operation:");
            System.out.println("1 - Add");
            System.out.println("2 - Subtract");
            System.out.println("3 - Multiply");
            System.out.println("4 - Divide");
            System.out.println("5 - Exit");

            System.out.print("Enter your choice: ");
            int option = input.nextInt();

            if (option == 5) {
                System.out.println("Thanks for using the calculator. Goodbye!");
                running = false;
                continue;
            }

            // Take numbers from user
            System.out.print("Enter the first number: ");
            double number1 = input.nextDouble();

            System.out.print("Enter the second number: ");
            double number2 = input.nextDouble();

            double result = 0;

            switch (option) {
                case 1:
                    result = add(number1, number2);
                    break;
                case 2:
                    result = subtract(number1, number2);
                    break;
                case 3:
                    result = multiply(number1, number2);
                    break;
                case 4:
                    result = divide(number1, number2);
                    break;
                default:
                    System.out.println("Invalid option. Please try again.");
                    continue;
            }

            System.out.println("Result: " + result);
        }

        input.close();
    }
}
