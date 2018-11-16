//Kamal Kakish
//This Program will create 2 users with an ID and account balance.
//It then withraws and deposits as instructed.
//It will deposit the set interest rates associated with each account.
//Then print the final balance using toString. 

import java.util.*;
import java.util.Date;

public class kakishk_Account { // default constructor
	private int id;
	private double balance;
	private double interestRate;
	private Date dateCreated;
	
	public kakishk_Account()
	{
		int id=0;
		double balance= 0.0;
		double interestRate = 0.0;
		dateCreated = new Date();
		
	}
	public kakishk_Account(int idnumber, double Balance, double interest) {
		this.id = idnumber;
		this.balance = Balance;
		this.interestRate = interest;
		this.dateCreated = new Date();
				
	}
	public Date getDateCreated() //getter
	{
		return dateCreated;
	}
public int getId() //getter
{
	return id;
}
public double getBalance() //getter
{
	return balance;	
}
public double getInterest() //getter
{
	return interestRate;
}
public void Withdraw(double amount) //Withdraw method
{
	balance -= amount;
}
public void Deposit(double deposit) { //Deposit Method
	balance += deposit;
}
public double getMonthlyInterest() { //Monthly Method
	double MonthlyRate = balance * interestRate;
	return MonthlyRate;
}

public String toString() { //toString Method
	return "ID: " + id + "; " + "Balance: $"+ balance +  "; " +
			"Rate: " + interestRate + "; " + "Date Created: "+ dateCreated + " ";



}}


//Prints the account using a toString Method
//Prints the account using withdraw/deposit method,
//along with applying interest
 public class kakishk_AccountTester {
public static void main(String[] args) {
	kakishk_Account account1 = new kakishk_Account( 1000, 20000, 0.045 );
	kakishk_Account account2 = new kakishk_Account( 1001, 10000, 0.06 );
	System.out.println(account1);
	account1.Withdraw(2500);
	account1.Deposit(account1.getMonthlyInterest());
	System.out.println(account1.toString());
	System.out.println(account2);
	account2.Deposit(3000);
	account2.Deposit(account2.getMonthlyInterest());
	System.out.println(account2.toString()); 
	
	
	}}
