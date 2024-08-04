# Codsoft-task
import java.util.Scanner;
import java.util.Random;

public class Codsoft1{

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        boolean playAgain = true;

        while (playAgain) {
            int targetNumber = random.nextInt(100) + 1;
            int attempts = 0;
            boolean hasGuessedCorrectly = false;
            final int MAX_ATTEMPTS = 10;

            System.out.println("I have generated a number between 1 and 100. Can you guess it?");

            while (!hasGuessedCorrectly && attempts < MAX_ATTEMPTS) {
                System.out.println("Enter your guess (attempt " + (attempts + 1) + " of " + MAX_ATTEMPTS + "): ");
                int guess = scanner.nextInt();
                attempts++;

                if (guess == targetNumber) {
                    hasGuessedCorrectly = true;
                    System.out.println("Congratulations! You guessed the correct number: " + targetNumber);
                } else if (guess < targetNumber) {
                    System.out.println("Too low! Try again.");
                } else {
                    System.out.println("Too high! Try again.");
                }
            }

            if (!hasGuessedCorrectly) {
                System.out.println("You've used all " + MAX_ATTEMPTS + " attempts. The correct number was: " + targetNumber);
            }

            System.out.println("Do you want to play again? (yes/no)");
            String response = scanner.next();
            if (!response.equalsIgnoreCase("yes")) {
                playAgain = false;
            }
        }

        System.out.println("Thank you for playing! Goodbye.");
        scanner.close();
    }
}

