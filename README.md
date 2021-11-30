## Number Guessing Game 

## Table of Contents 
- Introduction
- Materials Needed
- Getting Started with Eclipse
    - Once you install Java JDK
- Installation and Setup
- Inserting Source Code
- How to Play
- Code
- License
## _Introduction_

The following documentation gives instruction on how to get started and play the number guessing game.
- This game is written in [Java](https://docs.oracle.com/javase/8/docs/technotes/guides/language/index.html)
- The source code of this game can be found on [>hackr.io](https://hackr.io/blog/java-projects)


## Materials Needed

_This program works for both IOS and Windows OS._
- You need to have a Mouse or TouchPad to navigate your screen.
- You need to be connected to thee internet in order to get the source code.
- You must have a Keyboard with at least numbers 1-9 in order to guess your number.
- An IDE such as [Eclipse](https://www.eclipse.org/downloads/packages/release/kepler/sr1/eclipse-ide-java-developers) will be needed to play this game (more on this in the "Getting Started with Eclipse")


## Getting Started with Eclipse

> This game will run in [Eclipse](https://www.eclipse.org/downloads/packages/release/kepler/sr1/eclipse-ide-java-developers).
> Prior to downloading eclipse you will want to check if you have [Java JDK](https://www.oracle.com/java/technologies/downloads/#jdk17-windows) installed
>The easiest way to check if you have [Java JDK](https://www.oracle.com/java/technologies/downloads/#jdk17-windows) installed is 
- Opening _Command Prompt_
- Typing in "java -version" into your terminal and hitting enter
- This will tell you the version of java you have installed, if you do not have [Java JDK](https://www.oracle.com/java/technologies/downloads/#jdk17-windows) installed then it will not show what version you have.

    ![](https://cdn.discordapp.com/attachments/833448220620488795/910998507958177792/command.png)
- If you need to download [Java JDK](https://www.oracle.com/java/technologies/downloads/#jdk17-windows) then click on the link and follow the instructions from there. 
##### Once you have [Java JDK](https://www.oracle.com/java/technologies/downloads/#jdk17-windows) Installed
1. Begin by downloading [Eclipse](https://www.eclipse.org/downloads/packages/release/kepler/sr1/eclipse-ide-java-developers) 
 ![](https://cdn.discordapp.com/attachments/833448220620488795/911003955184693308/Copy.png)
 
 2. Open the .exe file located in the .zip folder
 ![](https://cdn.discordapp.com/attachments/833448220620488795/911005173747421214/copy2.png)

3. Now you have successfully downloaded and opened eclipse
   ![](https://cdn.discordapp.com/attachments/833448220620488795/911005754268454913/unknown.png)

## Installation
_The website that the source code is obtained from did not provide a .zip file for the game. So you will need to_ 
1. _Create a new Java Project in [Eclipse](https://www.eclipse.org/downloads/packages/release/kepler/sr1/eclipse-ide-java-developers)_
  ![](https://cdn.discordapp.com/attachments/833448220620488795/911008882120355940/copy5.png)
2. _Title this project "numberGuessingGame" with the "Use default location" option selected. Then select finish_
   ![](https://cdn.discordapp.com/attachments/833448220620488795/911010486429044836/Copty23.png)
3. _When prompted to create "module-info.java" file select "Don't Create"._
   ![](https://cdn.discordapp.com/attachments/833448220620488795/911011276346511410/Ogga.png)


4. _Next you will double click the file "numberGuessingGame", right click on the "src" file and select "new" then "class"._
   ![](https://cdn.discordapp.com/attachments/833448220620488795/911013824449097738/Boodod.png)


4. _When prompted to title your new class enter "GuessingGame" and select "finish"._
    ![](https://cdn.discordapp.com/attachments/833448220620488795/911017768709664798/proked.png)




## Setup

- Once you have your project set up in java you need to go and copy the source code from [>hackr.io](https://hackr.io/blog/java-projects) 
- Your Code should look identical to the example code below.
```
package numberGuessingGame;
import javax.swing.*;
 
public class GuessingGame {
    public static void main(String[] args) {
        int computerNumber = (int) (Math.random()*100 + 1);
        int userAnswer = 0;
        System.out.println("The correct guess would be " + computerNumber);
        int count = 1;

        while (userAnswer != computerNumber)
        {
            String response = JOptionPane.showInputDialog(null,
                "Enter a guess between 1 and 100", "Guessing Game", 3);
            userAnswer = Integer.parseInt(response);
            JOptionPane.showMessageDialog(null, ""+ determineGuess(userAnswer, computerNumber, count));
            count++;
        }  
    }

    public static String determineGuess(int userAnswer, int computerNumber, int count){
        if (userAnswer <=0 || userAnswer >100) {
            return "Your guess is invalid";
        }
        else if (userAnswer == computerNumber ){
            return "Correct!\nTotal Guesses: " + count;
        }
        else if (userAnswer > computerNumber) {
            return "Your guess is too high, try again.\nTry Number: " + count;
        }
        else if (userAnswer < computerNumber) {
            return "Your guess is too low, try again.\nTry Number: " + count;
        }
        else {
            return "Your guess is incorrect\nTry Number: " + count;
        }
    }
}
```
## How to Play

1. After you copy the source code into your java project you need to select the run option.
![](https://cdn.discordapp.com/attachments/833448220620488795/911059659505401876/dondond.png)
2. A window will appear asking you to choose a number between 1 and 100. 
3. Type in a value from your keyboard that is 1-100. 
4. If you guess wrong you will continue until you guess correctly, or click the cancel button to stop the game. 
![](https://cdn.discordapp.com/attachments/833448220620488795/911060334788354128/unknown.png)

## Code
##### import

- Importing javax.swing.* allows the use of JOptionPane and the creation of dialogue boxes.
```
import javax.swing.*;
```
##### main()
- The first thing we do in our main method is intitialize our 3 main variable and print our correct answer on the console.
```
        int computerNumber = (int) (Math.random()*100 + 1);
        int userAnswer = 0;
        System.out.println("The correct guess would be " + computerNumber);
        int count = 1;
```
- Next we create our while loop that determines when the the game will run.
- Checking to see if your answer matches the computer's random number between 1-100. 
- If you haven't guessed correctly it will prompt you to enter another number.
```
        while (userAnswer != computerNumber)
        {
            String response = JOptionPane.showInputDialog(null,
                "Enter a guess between 1 and 100", "Guessing Game", 3);
            userAnswer = Integer.parseInt(response);
            JOptionPane.showMessageDialog(null, ""+ determineGuess(userAnswer, computerNumber, count));
            count++;
        }  
```
##### determineGuess()
- This method is used to decide if the user's guess is 
   - Invalid
   ```
         if (userAnswer <=0 || userAnswer >100) {
               return "Your guess is invalid";
        }
    ```
   - Correct
   ```
         else if (userAnswer == computerNumber ){
                return "Correct!\nTotal Guesses: " + count;
        }
    ```
   - Too High
   ```
         else if (userAnswer > computerNumber) {
                return "Your guess is too high, try again.\nTry Number: " + count;
        }
    ```
   - Too Low
   ```
        else if (userAnswer < computerNumber) {
                return "Your guess is too low, try again.\nTry Number: " + count;
        }
    ```
   - Incorrect
   ```
        else {
                return "Your guess is incorrect\nTry Number: " + count;
        }
    ```

## License

This project is distributed by an [MIT license](https://opensource.org/licenses/MIT).

