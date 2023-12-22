# Dice
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Welcome to the Dice Rolling Game!");

        const int numberOfRounds = 3; // You can adjust the number of rounds as needed
        int player1TotalScore = 0;
        int player2TotalScore = 0;

        for (int round = 1; round <= numberOfRounds; round++)
        {
            Console.WriteLine($"\nRound {round}");

            int player1Roll = RollDice();
            int player2Roll = RollDice();

            Console.WriteLine($"Player 1 rolled: {player1Roll}");
            Console.WriteLine($"Player 2 rolled: {player2Roll}");

            player1TotalScore += player1Roll;
            player2TotalScore += player2Roll;

            Console.WriteLine($"Player 1 total score: {player1TotalScore}");
            Console.WriteLine($"Player 2 total score: {player2TotalScore}");
        }

        Console.WriteLine("\nGame Over!");

        if (player1TotalScore > player2TotalScore)
        {
            Console.WriteLine("Player 1 wins!");
        }
        else if (player1TotalScore < player2TotalScore)
        {
            Console.WriteLine("Player 2 wins!");
        }
        else
        {
            Console.WriteLine("It's a tie!");
        }
    }

    static int RollDice()
    {
        Random random = new Random();
        return random.Next(1, 7); // Rolls a random number between 1 and 6
    }
}
