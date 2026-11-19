
import java.util.Scanner;

public class StudentGradeTracker {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.println("================================");
        System.out.println("       STUDENT GRADE TRACKER");
        System.out.println("================================");

        System.out.print("Enter number of students: ");
        int n = sc.nextInt();
        sc.nextLine();

        String[] names = new String[n];
        int[] marks = new int[n];

        int total = 0;
        int highest = -1;
        int lowest = 101;

        int highIndex = 0;
        int lowIndex = 0;

        // Input student details
        for (int i = 0; i < n; i++) {

            System.out.print("Enter Student " + (i + 1) + " Name: ");
            names[i] = sc.nextLine();

            System.out.print("Enter " + names[i] + "'s Marks: ");
            marks[i] = sc.nextInt();
            sc.nextLine();

            total += marks[i];

            if (marks[i] > highest) {
                highest = marks[i];
                highIndex = i;
            }

            if (marks[i] < lowest) {
                lowest = marks[i];
                lowIndex = i;
            }
        }

        // Calculate average
        double average = (double) total / n;

        // Display report
        System.out.println("\n================================");
        System.out.println("         STUDENT REPORT");
        System.out.println("================================");

        System.out.println("Name\t\tMarks");

        for (int i = 0; i < n; i++) {
            System.out.println(names[i] + "\t\t" + marks[i]);
        }

        System.out.println("--------------------------------");
        System.out.println("Average Marks: " + average);
        System.out.println("Highest Marks: " + highest
                           + " (" + names[highIndex] + ")");
        System.out.println("Lowest Marks: " + lowest
                           + " (" + names[lowIndex] + ")");

        System.out.println("================================");

        sc.close();
    }
}
