# Square-root-of-a-number-
/* Square root of a number (Medium)

Given an integer x, find the square root of x. If x is not a perfect square, then return floor(√x).

Examples
Example 1:

Input:
x = 5
Output: 2

Example 2:

Input:
x = 4
Output: 2
*/
public class SquareRoot {
    public static int squareRoot(int x) {
        if (x == 0 || x == 1) {
            return x;
        }

        int start = 1, end = x, result = 0;

        // Binary search approach
        while (start <= end) {
            int mid = (start + end) / 2;

            // If x is a perfect square
            if (mid * mid == x) {
                return mid;
            }

            // Since we need floor, we update result when mid*mid is smaller
            // than x, and move closer to sqrt(x)
            if (mid * mid < x) {
                start = mid + 1;
                result = mid;
            } else {
                end = mid - 1;
            }
        }

        return result;
    }

    public static void main(String[] args) {
        int x1 = 5;
        System.out.println("Square root of " + x1 + " is: " + squareRoot(x1));  // Output: 2

        int x2 = 4;
        System.out.println("Square root of " + x2 + " is: " + squareRoot(x2));  // Output: 2
    }
}
