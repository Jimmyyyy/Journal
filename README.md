# Journal

Jimmy Wu

5/4/17

Today we are deciding between which games we would actually make. We have decided 2048 was not the best choice
for us to display our skills.

5/5/17

Today we have finally decided on exactly what we will do. We will make a game similar to the plague inc game. We will be doing the entire project in java.

5/8/17

My group is thinking of what parts of the actual game to implement into our own. For example, the actual game shows a plane moving from one country to another when the disease is on the plane. We have decided to use that for our game as well. Tracey and Wendy will be working on spreading the disease while Joseph and me will be working on cure. Ivan is working on gui and looks.

5/9/17

Ivan and I started coding our classes. I have also decided to do the news class which will be part of the game that displays what the current state/news is occuring around the world. The news will change according to the current time and date of the game. Since I will be doing the cure as well, once the cure starts, the news will display that scientists are currently working on a cure. 

5/10/17

I will start working on the map of the U.S so we can use that as our background for the game. Also, each state will have 5 different dollars. Everytime the percentage of the total population of the state that is infected increases by 25 percent, the state will turn to a darker shade of red until it reaches 100 percent where it will be the darkest shade of red. Once the entire population is killed, the state will turn black. If the state's population is 100 percent healthy, it will be the normal color of green. 
Also started adding the news text.

5/11/17

Today Joseph, Ivan and I worked together on the cure class. We have decided to use percentages of the population in order to activate the cure. For example, if 10 percent of the entire population is infected, a message will display that recently, there has been a disease spreading around. Once the percent hits 20, the cure will start.

5/12/17 

Continued working on news class. Added more news and created getters.

5/15/17

Joseph, Ivan and I got a working test cure class running that counts every 2 seconds as a day and we were also able to call a method from the cure class every 2 seconds to check if the cure should start or not. Tomorrow we will start programming how the cure class works after it runs.

5/16/17

Today I worked on the isDetected method in the cure class.

5/17/17

Today Joseph completed his method that counts the months and days correctly. I was able to use this method to implement it into my cure class so every 10 days, the cure will increase by 1 percent.

5/18/17

Today Joseph and I were able to make a method that calculates the remaining time we have before the cure is 100 percent completed.

5/22/17 

Worked on the cure class and improved isDetected method.

5/23/17

Joseph and I were able to complete the accurate calculation of how long it would take to complete the cure. It now also calculates the days left instead of just years.

5/24/17

Today Joseph and I were able to debug an error where it would take 20 days to make the cure percentage increase. Once enough people are infected, the days should change to 15 but instead it turns to 5 and then 15.

5/30/17

Added more news statements for the news class.

5/31/17

Made it possible to display a screen and also print the dates on the console. We just have to try and print the dates onto the screen now.

6/1/17

Rewrote some missing lines of code that was missing since we didn't push.

6/2/17 

Added what would happen to the cure class once curePercentage increases to 100.

6/5/17

Finished with what the cure class would do once cure Percentage increases to 100. 

6/6/17

package Jimmy;

import Wendy.State;

public class Cure {
	
	private int curePercentage= 0;
	private double infectedPercentage = 0;
	private double popDeadPercentage;
	
	public boolean activate = false;
	private int counter = 0;	
	private int counter2 = 0;
	private int counter3 = 0;
	private int counter4 = 0;
	private int counter5 = 0;
	private boolean win = true;
	public Cure() {
		
	}
	
	public boolean getWin() {
		return win;
		
	}
	
	public void isDetected(){
		//while every second passes
		//infected = State.getInfectedpop
		
//		if(infectedPercentage == 0 && counter4 == 1) {
//			System.out.println("The diseased has been erased from this world. You have lost");
//			win = false;
//		}
		if (curePercentage < 100 && counter < 1) {
			
			if(infectedPercentage > 10) {
			
				if(counter5 < 1) {
					System.out.println("cure has started");
					counter5++;
				}
				
				if(infectedPercentage == 100) {
					cureBase(5);
					infectionBase(5);
				}else if (infectedPercentage >= 60){
					cureBase(10);
					infectionBase(10);
				}else{
					cureBase(20);
					infectionBase(20);
				}
				
					
			}
			
			else if(infectedPercentage >= 0 && infectedPercentage <= 10){
				
				if (infectedPercentage == 10) {
					if (counter2 < 1) {
						System.out.println("A new disease is discovered in the us");
						counter2++;
					}
					
					infectionBase(30);
				}else {
					infectionBase(30);
				}
				
			}
			
		}else{
			
			if(counter3 < 1) {
				System.out.println("Cure has been completed and is being delivered around the world");
				counter3++;
				counter++;
			}
			spreadCure(1);
			System.out.println("Infected percentage is now " + infectedPercentage);
			
		}
			
	}
	
	
	
	public void makingCure(int rate){
		int a = (rate * 100);
		int b = (a - curePercentage*rate);
		if(curePercentage == 100){
			System.out.println("Cure is done!!");
		}	
		else if(a == 0){
			System.out.println("No Cure is currently being made");
		}



		else if(b < 365){

			System.out.println("Cure will be completed in " + b + " day(s)");
		}

//		else{
//			System.out.println("Cure will be completed in " + b/365 + " year(s)");
//		}

		else{
			System.out.println("Cure will be completed in " + b/365 + " year(s)");
		}

		
	}
	
	public void infectionBase(int base) {
		if(Sleeper.ten % base == 0 ){
			if(infectedPercentage < 100) {
				infectedPercentage++;
			}
		}
		System.out.println("Infected percentage is " + infectedPercentage + "%");
	}
	
	public void cureBase(int base) {
		if(Sleeper.ten % base == 0 ){
	
		curePercentage++;

		
		
		
		


		makingCure(base);
	 
		}
		System.out.println("cure is " + curePercentage + "% completed");
	}	
	
	public void spreadCure(int base){
		if(Sleeper.ten % base == 0 ){
			infectedPercentage--;
			System.out.println(infectedPercentage + "% infected :(");
			
		}		
	}
}

6/7/17

Completed cure class more.
