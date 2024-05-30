# CODESOFT---PROJECT(TASK-1)
// NUMBER-GAME
import java.util.*;
public class main{
    public static void main (String[] args){
        Scanner sc=new Scanner(System.in);
        Random random=new Random();
        int minR=1; // Minimum Range for the random number
        int maxR=100; //Maximum Range for the random number
        int maxAttempts=3; //Maximum Attempts for the number
        int score=0; 
        boolean playAgain=true;
        while(playAgain){
            int tasknum=random.nextInt(maxR-minR+1)+minR;
            int attempts=0;
            System.out.println("\n Guessing number between"+ minR+" and "+maxR+".");
            System.out.println("You have "+ maxAttempts+ " attempts to guess your number ...");
            for(int i=1;i<=maxAttempts;i++){
                System.out.print(i);
                int userGuess=sc.nextInt();
                attempts++;
                if (userGuess==tasknum){
                    System.out.println("Hurrah!... you Guess the right Number in"+attempts+"attempts.");
                    score+=(maxAttempts-attempts)+1;
                    break;
                    }
                else if(userGuess<tasknum){
                    System.out.println("Low!..., Try Again!...");
                }  
                else{
                    System.out.println("High!..., Try Again!...");
                }
                if(attempts==maxAttempts){
                    System.out.println("Oops!...., you've used all your attempts.The number was: "+tasknum);
                }
            }
            System.out.print("\n Do you want to play again?....  ");
            String choice=sc.next().toLowerCase();
            playAgain=choice.equals("Yes") || choice.equals("No"); 
        }
        System.out.println("\n your total score is: "+score+ "\n Thanks for playing the NUMBER GAME!....");
        
    }
}
