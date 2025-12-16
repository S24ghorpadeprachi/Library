# Library
/*This mini project is a console-based Library Management System developed using Java. It allows the user to manage a collection of books using arrays and the Arrays class. The system enables users to add book names, display the book list, search for a book, sort books alphabetically, */
import java.util.Arrays;
import java.util.Scanner;

public class LibrarySystem {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of books: ");
        int n = sc.nextInt();
        sc.nextLine(); // consume newline

        String books[] = new String[n];

        System.out.println("Enter the names of the books:");
        for (int i = 0; i < n; i++) {
            System.out.print("Book " + (i + 1) + ": ");
            books[i] = sc.nextLine();
        }

        // Display book list
        System.out.println("\nBooks in Library:");
        System.out.println(Arrays.toString(books));

        // Search a book
        System.out.print("\nEnter a book name to search: ");
        String search = sc.nextLine();

        boolean found = false;
        for (String b : books) {
            if (b.equalsIgnoreCase(search)) {
                found = true;
                break;
            }
        }

        if (found)
            System.out.println("Book is AVAILABLE in the library.");
        else
            System.out.println("Book is NOT available.");

        // Sort book list alphabetically
        Arrays.sort(books);
        System.out.println("\nSorted Book List:");
        System.out.println(Arrays.toString(books));

        // Update a book
        System.out.print("\nDo you want to update a book name? (yes/no): ");
        String choice = sc.nextLine();

        if (choice.equalsIgnoreCase("yes")) {
            System.out.print("Enter book number to update: ");
            int index = sc.nextInt() - 1;
            sc.nextLine();

            if (index >= 0 && index < n) {
                System.out.print("Enter new book name: ");
                books[index] = sc.nextLine();
                System.out.println("Updated Book List:");
                System.out.println(Arrays.toString(books));
            } else {
                System.out.println("Invalid book number!");
            }
        }
    }
}
