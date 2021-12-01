# Checking-Account-Java-project
/**
 * CheckingAccount here.
 *
 * @author Gregory White
 * @version April 8th
 */

import java.util.ArrayList;
public class CheckingAccount extends Account
{
    //ArrayList holds checks
   ArrayList<Integer> checkList;
   public CheckingAccount(){
       super();//super is creating the account
       checkList = new ArrayList<Integer>();
    }
    public CheckingAccount(double money){
        super(money);
        checkList = new ArrayList<Integer>();
    }
    //verifies to see if checks are good
   public void processCheck(int checknum, double money){
       boolean goodCheck = true;
       for(int i : checkList){
           if (i == checknum){
               goodCheck = false;
            }
        }
        if (goodCheck == true){
            withdraw(money);
            checkList.add(checknum);
        }
        else{
            System.out.println("ALERT: Check number "  + Integer.toString(checknum) + " has already been processed!");
        }
    }
    @Override
    public String toString(){
        String money;
        money = "Checking Account:";
        money = money + "\nBalance: $" + Double.toString(this.balance);
        money = money + "\nProcessed checks: ";
        for(int i: checkList){
            money = money + " " + Integer.toString(i);
        }
        return money +"\n";
    }
    

}
