# Suming-numbers
This project processes and sums all digits entered into the main method and prints the total, example: For example calling the method sumDigits(125) should return 8 since 1 + 2 + 5 = 8.

public class DigitSumChallenge {
    public static int ERROR_MESSAGE = -1;

    public static int sumDigits(int number) {

        if (number < 10) {
            return ERROR_MESSAGE;
        }
        int separator = number % 10;
        int digitOne = number / 10 % 10;
        int digitTwo = number / 10 / 10 % 10;
        int digitThree = number / 10 / 10 / 10;
        int addItAll = separator + digitOne + digitTwo + digitThree;

        if (number >= 10000) {
            int highNumbers = number / 10;
            int highNumbersBal = number % 10;

            return  sumDigits(highNumbers) + highNumbersBal;
        }

        return addItAll;
    }

    public static void main(String[] args) {
        System.out.println(sumDigits(5234675));
    }
}
