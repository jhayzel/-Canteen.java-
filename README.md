```java
import java.util.Scanner;

public class CanteenOrderingSystem {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String[] items = {
            "Macaroni Salad", "Chicken Burger", "Carbonara",
            "Empanada", "Lomi"
        };

        double[] price = {80, 120, 130, 50, 100};
        double[] studentPrice = {70, 100, 110, 40, 90};

        double total = 0;
        int totalQty = 0;

        System.out.println("=== CANTEEN ORDERING SYSTEM ===");

        for (int i = 0; i < items.length; i++)
            System.out.printf("%d. %s - PHP %.2f%n",
                    i + 1, items[i], price[i]);

        System.out.print("Are you a student? (Y/N): ");
        boolean student = sc.next().equalsIgnoreCase("Y");

        String again = "Y";

        while (again.equalsIgnoreCase("Y")) {
            System.out.print("Enter item number (1-5): ");
            int item = sc.nextInt();

            System.out.print("Enter quantity (1-10): ");
            int qty = sc.nextInt();

            double p = student ? studentPrice[item - 1] : price[item - 1];
            double amount = p * qty;

            total += amount;
            totalQty += qty;

            System.out.printf("Order: %d x %s = PHP %.2f%n",
                    qty, items[item - 1], amount);

            System.out.print("Order again? (Y/N): ");
            again = sc.next();
        }

        System.out.println("\n=== ORDER SUMMARY ===");
        System.out.println("Student: " + (student ? "Yes" : "No"));
        System.out.println("Total quantity: " + totalQty);
        System.out.printf("Total amount: PHP %.2f%n", total);
        System.out.printf("Final amount: PHP %.2f%n", total);

        System.out.println("Thank you for ordering!");

        sc.close();
    }
}
```
