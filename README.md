import java.util.Scanner;

public class SimpleLogin {
    public static void main(String[] args) {
        // Correct login details
        String correctUsername = "admin";
        String correctPassword = "12345";

        // Allow 3 tries
        int attempts = 3;

        Scanner sc = new Scanner(System.in);

        while (attempts > 0) {
            // Ask for username
            System.out.print("Enter username: ");
            String username = sc.nextLine();

            // Ask for password
            System.out.print("Enter password: ");
            String password = sc.nextLine();

            // Show password as stars (same length as entered)
            System.out.print("Password entered: ");
            for (int i = 0; i < password.length(); i++) {
                System.out.print("*");
            }
            System.out.println(); // move to next line

            // Check login
            if (username.equals(correctUsername) && password.equals(correctPassword)) {
                System.out.println("Login successful! Welcome " + username);
                return; // stop program after success
            } else {
                attempts--; // reduce attempts
                System.out.println("Invalid login. Attempts left: " + attempts);
            }
        }

        // If all attempts used
        System.out.println("Too many failed attempts. Access denied.");
        sc.close();
    }
}
