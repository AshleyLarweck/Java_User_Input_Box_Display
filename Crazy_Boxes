import java.awt.*;
import java.util.Random;
import java.util.Scanner;

public class CrazyBoxes {

    public static void drawBoxWText(Graphics g, int numTimes, String str2Print, DrawingPanel panel, 
                                    int [] xPosition, int [] yPosition, int current, Color colorValue, 
                                    int choiceValue) {

        // initializing color array
        Color[] colorArray = {Color.BLUE, Color.CYAN, Color.DARK_GRAY, Color.GRAY, Color.GREEN, 
                              Color.LIGHT_GRAY, Color.MAGENTA, Color.ORANGE, Color.PINK, Color.RED, Color.YELLOW};
        final int HEIGHT = 30; //initializing constant value for box HEIGHT
        int WIDTH = g.getFontMetrics().stringWidth(str2Print) + 10; //initializing WIDTH value to change based on the size of the string, with 10/2 pixels added to each side  of the string

        for (int i = 0; i < numTimes; i++){
            if (choiceValue == 1){ //if the user selects to "keep" the text after the color flash
                
                //set color & fill rectangle with color based on random selection from colorArray at random position(s) X & Y
                g.setColor(colorValue);
                g.fillRect(xPosition [current], yPosition[current], WIDTH, HEIGHT);
                //set string font color to white 
                g.setColor(Color.WHITE);
                //draw string at X & Y coordinates from StringXCoordinate & StringYCoordinate arrays -- adjusted from x/y coordinate values in main method, to be centered & full visible within panel
                g.drawString(str2Print, xPosition [current] + 5, yPosition [current] + (30 * 2 / 3));
                //sleep graphical object for .05 seconds
                panel.sleep(50);
                //change color of the box from random color to WHITE 
                g.fillRect(xPosition [current], yPosition[current], WIDTH, HEIGHT);
                //change string text color from WHITE to BLACK, to keep text visible once box disappears
                g.setColor(Color.BLACK);
                //draw string again, but in current text color (BLACK)
                g.drawString(str2Print, xPosition [current] + 5, yPosition [current] + (30 * 2 / 3));
            }
            else if (choiceValue == 0){ //if the user selects NOT to "keep" the text after the color flash
                
                //set color & fill rectangle with color based on random selection from colorArray at random position(s) X & Y
                g.setColor(colorValue);
                g.fillRect(xPosition [current], yPosition[current], WIDTH, HEIGHT);
                //set string font color to white 
                g.setColor(Color.WHITE);
                //draw string at X & Y coordinates from StringXCoordinate & StringYCoordinate arrays -- adjusted from x/y coordinate values in main method, to be centered & full visible within panel
                g.drawString(str2Print, xPosition [current] + 5, yPosition [current] + (30 * 2 / 3));
                //sleep graphical object for .05 seconds
                panel.sleep(50);
                //draw box again, but in current set color (WHITE)
                g.fillRect(xPosition [current], yPosition[current], WIDTH, HEIGHT);     
                }

    }
}
    public static void main(String[] args) {
      
        //define scanner, random, drawing panel, graphics
        Scanner scnr = new Scanner(System.in);
        Random rand = new Random();
        DrawingPanel panel = new DrawingPanel(500, 400);
        Graphics g = panel.getGraphics();

        //my name
        System.out.println("UTSA - Summer 2020 - CS1083 - Project 2 - written by ASHLEY LARWECK");
        //user prompts & scanner recieves user input
        System.out.println("Please, enter a string with no whitespace: ");
        String userString = scnr.next();
        System.out.println("Please, enter a number (1 to 15): ");
        int userNum = scnr.nextInt();
        System.out.println("Do you want to leave the text? (1-Yes, 0-No): ");
        int userChoice = scnr.nextInt();
        
        //initializing X & Y coordinate arrays & color identifier to store random colors from colorArray
        int[] xCoordinate = new int[userNum];
        int[] yCoordinate = new int[userNum];
        Color color;
        
        //initializing colorArray
        Color[] colorArray = {Color.BLUE, Color.CYAN, Color.DARK_GRAY, Color.GRAY, Color.GREEN, 
            Color.LIGHT_GRAY, Color.MAGENTA, Color.ORANGE, Color.PINK, Color.RED, Color.YELLOW};    
        
        //while-loop to accept user input values only within range 1-15
        while (userNum < 1 || userNum > 15) {
            System.out.println("Please, enter a number (1 to 15): ");
            userNum = scnr.nextInt();
            }
        //while-loop to accept user input values only within range 0-1
        while (userChoice != 0 && userChoice != 1){
            System.out.println("Do you want to leave the text? (1-Yes, 0-No): ");
            userChoice = scnr.nextInt();
            }
        
            if (userChoice == 1){ //if the user selects to "keep" the text
                for (int i = 0; i < userNum; i++){
                    //random X coordinate for box to be drawn in drawBoxWText method 
                    //random value range adjusted to ensure box remains visible within panel
                    xCoordinate [i] = rand.nextInt(501 - (g.getFontMetrics().stringWidth(userString) + 10)); 
                    //Y coordinate for box to be drawn in drawBoxWText method 
                    //random value range adjusted to ensure box remains visible within panel
                    yCoordinate [i] = rand.nextInt(401 - 30); 
                    //random color selected and stored
                    color = colorArray [rand.nextInt(colorArray.length)];
                    //method call
                    drawBoxWText(g, userNum, userString, panel, xCoordinate, yCoordinate, i, color, userChoice);
                    }
            }
            
            else if (userChoice == 0){ //if the user selects NOT to "keep" the text
                for (int i = 0; i < userNum; i++){
                    //random X coordinate for box to be drawn in drawBoxWText method 
                    //random value range adjusted to ensure box remains visible within panel
                    xCoordinate [i] = rand.nextInt(501 - (g.getFontMetrics().stringWidth(userString) + 10));
                    //Y coordinate for box to be drawn in drawBoxWText method 
                    //random value range adjusted to ensure box remains visible within panel
                    yCoordinate [i] = rand.nextInt(401 - 30); 
                    //random color selected and stored
                    color = colorArray [rand.nextInt(colorArray.length)];
                    //method call
                    drawBoxWText(g, userNum, userString, panel, xCoordinate, yCoordinate, i, color, userChoice);
                    }
        }
     
        for (int i = 0; i < userNum; i++){ //prints iteration & random X-Y coordinates
            System.out.println(i + " - (" + xCoordinate [i] + " , " + yCoordinate [i] +")");
            }




}


}
