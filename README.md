# Lab-Nim
import java.util.Scanner; //imports Scanner to program
/**
 * 10-23-18
 *I pledge that I have neither given nor received prohibited aid on this assessment.
 *-Sarah and Gabby
 */
public class nim
{
    static Scanner in = new Scanner(System.in);   
    public static void main(String [] args){ //main method 
        System.out.println("Player one, enter your name."); //asks a user to input their name
        String playerOne = in.nextLine();
        System.out.println("Player two, enter your name."); //asks 2nd user to input their name
        String playerTwo = in.nextLine();
        
        int counter = 0;//setting the counter equal to 0 & counter is counting how many times the user inputs a number from 0
        
        greeting();//calls greeting method
        
        System.out.println("How many sticks do you want to start with?");//asks user to input any number of sticks
        int n = in.nextInt();
        while (n > 0){//conditional loop for each turn 
                printSticks(n);//calls printSticks method
                System.out.println( );
                System.out.println("How many sticks do you want to remove?");
                int x = in.nextInt();
              
                if(x != 1 && x != 2 )//if the user's input isn't 1 or 2 then the program will print what it below
                {
                    System.out.println("you can only remove 1 or 2 sticks");
                }
                else {//if the user's input is 1 or 2 then it will subtract their number (x) from the number of sticks (n)
                    n = n - x;
                    counter ++;
               }
               
            }
        winner(playerOne, playerTwo, counter);//calling winner method 
        }
    public static void greeting(){
        System.out.println("Hi! I want to play Nim. Do you know how to play?");//going over instructions for the game
        String response = in.nextLine();
        if (response.equals("yes"))
        {
           System.out.println("Ok! Let's Begin!");
        }
        else if (response.equals("no"))//if no, then program will explain the game to the user
        {
          System.out.println("That's ok! Here's how: "); 
          System.out.println("1. Choose number of sticks to start with."); 
          System.out.println("2. Choose to take away either 1 or 2 sticks on your turn"); 
          System.out.println("3. Your opponent will then go and take sticks away");
          System.out.println("4. Whoever takes away the last stick looses"); 
        }
        }
    public static void printSticks(int n){  //prints number of sticks using for Loop 
            for(int x = 0; x < n; x ++){//until the number of sticks equals the user's input, the program will keep adding sticks
                System.out.print("|");
            }
     }
    public static void winner (String first, String second, int counter){//passes winner names and counter value to winner value
         if (counter %2 == 0)//announces winner
            {
               System.out.println(first + ", you won!");
            }
        else if (counter %2 != 0)//announces winner
        {
               System.out.println(second + ", you won!"); 
            }
        }
    }
