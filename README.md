import java.io.FileWriter;
import java.io.BufferedWriter;
import java.io.IOException;
public class Qfour
{
    public static void main (String args[]) throws IOException{
        Boolean[] lotteryNumbers = new Boolean [51];
        int numberofselectedBalls = 0;
        int winningBall;
        while (numberofselectedBalls != 6){
            do {
                winningBall = (int) (Math.random() *50);


            }
            while (winningBall == 0);
            if (lotteryNumbers [winningBall] == false){
                lotteryNumbers[winningBall] = true;
                numberofselectedBalls++;
            }
        }
        FileWriter fw = new FileWriter ("lottery.txt", true);
        BufferedWriter bw = new BufferedWriter(fw);
        for (int i=1; i<50; i++) {
            if (lotteryNumbers[i] == true){
                fw.write(i + "/t");
            }
        }
        fw.close();
    }


}
