# LA1400

```java

package AngelAngelov;
import robocode.*;


public class Bouncer extends JuniorRobot
{
    int players = others;
	public void run() {
	
            setColors(white, red, white, gray, white);
            int players = others;
	    //the players alive determines the movment 
           while(true) {
           if (players > 5){
           bounceMode();
          }else if(players < 5) {
           crazymode();
          }else if(energy < 20){
           safemode();
          }	
		}
     }
	public void onScannedRobot() {
     bearGunTo(scannedBearing);
     fire(3); 
	}
	//not complit, second part by onhitonwall 
    public void bounceMode() {
		ahead(5000);
		turnGunRight(360);	
	}
	public void crazymode(){
		    ahead(240);
            turnGunRight(100);
            back(80);
            turnGunLeft(360);
            ahead(160);
			out.println("boink");
	}
	public void safemode() {
		back(fieldHeight / 2);
            turnRight(180);
            ahead(fieldHeight / 4);
            turnRight(90);
	}
	public void onHitByBullet() {
	  if(players < 5){
		  turnRight(hitByBulletAngle);
		turnGunRight(hitByBulletAngle);
	  }
      
	}	// this is also part of the bounce mode, so if it touches somthing it turns
	public void onHitWall() { 	
		if(players > 5) {
			turnRight(90);
		}else{
           turnRight(90);
		   ahead(100);
        }
	}
		public void onWin() {
		while(true){
	    turnRight(180);
		turnLeft(180);
		out.println("You can't defeat me!!!");
		}       
	}	
}
```
