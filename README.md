import java.util.Scanner;

public class Calculator {

    public static void main(String[] args) {

        double num1, num2, result;
        char operator;

        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter first number: ");
        num1 = scanner.nextDouble();

        System.out.print("Enter second number: ");
        num2 = scanner.nextDouble();

        System.out.print("Enter an operator (+, -, *, /): ");
        operator = scanner.next().charAt(0);

        scanner.close();

        switch (operator) {
            case '+':
                result = num1 + num2;
                break;

            case '-':
                result = num1 - num2;
                break;

            case '*':
                result = num1 * num2;
                break;

            case '/':
                if (num2 != 0) {
                    result = num1 / num2;
                } else {
                    System.out.println("Error! Division by zero is not allowed.");
                    return;
                }
                break;

            // operator doesn't match any case constant (+, -, *, /)
            default:
                System.out.println("Error! Invalid operator. Please enter correct operator.");
                return;
        }

        System.out.printf("%.1f %c %.1f = %.1f\n", num1, operator, num2, result);
    }
}
