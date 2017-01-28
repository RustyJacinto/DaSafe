# DaSafe
Stuff that holds my programs
package com.company;
import java.util.Random;
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
	                //Variables, randoms, scanners, and stuff//
        Random rndm = new Random();
        Scanner input = new Scanner(System.in);
        int comp, playerPick=0;
        String userName, choose, playerChoice="woohoo", compChoice="woohoo", retry = "woohoo";
        char select='r', retryPt2='y';

                                //Game reseter (for when player retrys)//
        while (retryPt2 == 'y') {               //<-- to restart program if player wants to play again
            int win=0, lose=0, tie=0;           //<--- To reset result counter

                                //Rock, Paper, Scissors (Player pick)//
            System.out.println("Choose rock (r), paper(p), or scissors(s)");
            choose = input.nextLine();
            choose = choose.toLowerCase();
            select = choose.charAt(0);
            select = select;

                                     //Pick check//
            while (select != 'r' && select != 'p' && select != 's') {
                System.out.println("Bruh, pick rock (r), papaer (p), or scissors (s).");
                choose = input.nextLine();
                choose = choose.toLowerCase();
                select = choose.charAt(0);
            }

                            //Rock, Paper, Scissors (Player pick) continued//
            if (select == 'r') {
                playerPick = 1;
                playerChoice = "rock";
            } else if (select == 'p') {
                playerPick = 2;
                playerChoice = "paper";
            } else if (select == 's') {
                playerPick = 3;
                playerChoice = "scissors";
            }

                            //Rock, paper, scissors (Computer pick)//
            comp = rndm.nextInt(3) + 1;

            if (comp == 1) {
                compChoice = "rock";
            } else if (comp == 2) {
                compChoice = "paper";
            } else if (comp == 3) {
                compChoice = "scissors";
            }

                                        //Results: Player Wins//
            if (playerPick == 1 && comp == 3) {
                System.out.println("You chose " + playerChoice + " and the computer picked " + compChoice + ".");
                System.out.println("Your rock pulled the Dwayne Johnson on the computer's scissors.");
                win++;
            } else if (playerPick == 2 && comp == 1) {
                System.out.println("You chose " + playerChoice + " and the computer picked " + compChoice + ".");
                System.out.println("You gave the computer's rock a mean paper cut.");
                win++;
            } else if (playerPick == 3 && comp == 2) {
                System.out.println("You chose " + playerChoice + "and the computer picked " + compChoice + ".");
                System.out.println("You bust out the Genji katana on computer's papaer.");
                win++;
            }

                                        //Results: Computer Wins//
            else if (playerPick == 1 && comp == 2) {
                System.out.println("You chose " + playerChoice + " and the computer picked " + compChoice + ".");
                lose++;
            } else if (playerPick == 2 && comp == 3) {
                System.out.println("You chose " + playerChoice + " and the computer picked " + compChoice + ".");
                lose++;
            } else if (playerPick == 3 && comp == 1) {
                System.out.println("You chose " + playerChoice + " and the computer picked " + compChoice + ".");
                lose++;
            }

            //Results; Tie//
            else if (playerPick == comp) {
                System.out.println("You chose " + playerChoice + " and the computer picked " + compChoice + ".");
                tie++;
            }

            //I made a counter for winning, losing, and ties so it's easier to code later on.

                                        //End Screen//
            if (win == 1) {
                System.out.println("You win! (>^_^)b");
            } else if (lose == 1) {
                System.out.println("You lose! :c");
                System.out.println("The computer showed you who was boss of this gym. <(v_v)>");
            } else if (tie == 1) {
                System.out.println("It's a tie! D:");
            }

                                        //Play Again?//
            System.out.println("Play again? (Yes (y) or No (n)?");
            retry = input.nextLine();
            retry = retry.toLowerCase();
            retryPt2 = retry.charAt(0);

            //Input checker//
            while (retryPt2 != 'y' && retryPt2 !='n') {
                System.out.println("Play again? (Yes (y) or No (n)?");
                retry = input.nextLine();
                retry = retry.toLowerCase();
                retryPt2 = retry.charAt(0);
            }
        }
        System.out.println("Thank you for playing. ^_^");

    }
}
