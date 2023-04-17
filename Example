package org.example;

import java.util.Arrays;

public class Example {

//        Given a dollar amount, calculate the least amount of coins that would be necessary to fulfill the amount?
//        Examples:
//        Input: 1
//        Output: [4 quarters, 0 dimes, 0 nickels, 0 cents]
//        Input: 0.90
//        Output: [3 quarters, 1 dimes, 1 nickels, 0 cents]
//        Input: 4.76
//        Output: [19 quarters, 0 dimes, 0 nickels, 1 cents]
//        Quarter = 0.25
//        Dime = 0.10
//        Nickle = 0.05
//        Cent = 0.01

    // Coins values
    static int Quarter = (int)(0.25 *100);
    static int Dime = (int)(0.10 *100);
    static int Nickle = (int)(0.05 *100);
    static int Cent = (int)(0.01 *100);

    // a static array containing the coin values
    static int[] coins = new int[]{Quarter, Dime, Nickle, Cent};



    public static void main(String[] args) {
        System.out.println(Arrays.toString(recursiveAmountOfCoins(1)));
        System.out.println(Arrays.toString(recursiveAmountOfCoins(0.9)));
        System.out.println(Arrays.toString(recursiveAmountOfCoins(4.76)));
    }



    // Recursive methods
    static public int[] recursiveAmountOfCoins(double dollar){

        /*

        Call the recursive method that receive 3 params:
        1. An empty array where the amount of coins will accumulate
        2. The remaining dollar amount to calculate, in the first call we send the initial dollar amount * 100
        3. The index of the coin that will be calculated, in the first call we send the Quarter coin index 0

         */
        return recursiveAmountOfCoins(new int[4], (int)(dollar*100), 0);
    }

    static public int[] recursiveAmountOfCoins(int[] coinsArray, int remain, int coin){
        // Stop condition, if the remaining is 0 them return the accumulated coinsArray
        if(remain == 0)
            return coinsArray;

        // The amount of coins is calculated according the remaining money
        coinsArray[coin] = remain / coins[coin];

        // Re-call of the recursive function, replacing "remain" param with the module of remain and actual coin value and increasing the "coin" value in 1
        return recursiveAmountOfCoins(coinsArray,remain % coins[coin], coin + 1);
    }


    // Method without recursion
    static public int[] amountOfCoins(int dollar){

        int[] coins = new int[4];
        int remaining = dollar;


        coins[0] = (int) (remaining / Quarter);
        remaining =  (int) (remaining % Quarter);

        coins[1] = (int) (remaining / Dime);
        remaining =  (int) (remaining % Dime);

        coins[2] = (int) (remaining / Nickle);
        remaining =  (int) (remaining % Nickle);

        coins[3] = (int) (remaining / Cent);
        remaining =  (int) (remaining % Cent);


        return coins;
    }


}
