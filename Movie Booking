/*********************************************************************************************************************************************************
 *Project Name: Movie_booking.cpp
 
 *Description: A list of 9 movies which can be booked by a user at 5 different time sets. One person can book multiple tickets as long as the
               people meet the age criteria. The output, that is the ticket details would be given in the form of a text file.
 
*Program:A movie booking system which uses OOP concepts like Data Abstraction, Encapsulation and Inheritance. The program contains two classes
              one with the movie details, with name, tickets left age rating and starting time. This 'Movies' class is a parent class to the child
              class customer_details, in which one function allows people to enter their details and the other allows gives them a ticket in the
              form of a text file.

***********************************************************************************************************************************************************/


/**********************************************************************************************************************************************************
Date: 11 May 2020

Name: Shreyas Ramani

************************************************************************************************************************************************************/
/*Header Files needed*/
/***********************************************************************************************************************************************************/
#include<iostream> //input/output
#include<fstream> //for file handling
#include<string.h>//for string functions
/***********************************************************************************************************************************************************/
using namespace std; 

class Movies    //parent class, contains 4 public members about movie details in that particular theatre
{
	public:  //declaring members public
	
	string movie_name[30]={"Terminator", "The Matrix","Inception","The Lion King","Fast and Furious","Back to the Future","Rocky","Indiana Jones","Pulp Fiction"};
	//List of movies available in the theatre.
	int tickets_left[30]={11,14,10,8,9,17,9,12,13};
	//tickets remaining in the given movies in the above list.
	int age_rating[30]={18,13,13,3,15,7,15,13,18};
	//age rating for each movie in the list.
	string time[30]={"9:45","12:00","3:30","6:20","9:00"};
	//start times in general. This isn't for each movie, each movie has all five slots.

}; // end of class


class customer_details : public Movies //child class which is a public derivative of the parent class Movies.
{   
    //private members
	string name[30];
	//Enter names of people wanting to watch the movie.
	int age[30];
	//Entering the age of people wanting too watch the movie.
	int movie_num;
	//movie_num is a number given to each movie to help the user choose the right movie.
	int num_ticket;
	//number of tickets customer wants to book.
	int time_number;
	//numbers are given to different time slots for the user to choose.

	
	public:  //public members
		
		void enter_details();
		//this function is for user to enter hsi/her details.
		void display_details();
     	//this function is to show the results in form of a text file.
     	
};// end of class.

void customer_details::enter_details() //accessed using scope resolution
{
	int flag1=1; //this is to check whether the movie is age appropriate to people who applied.
	
	int flag2=1; //this is to check whether tickets are remaining for the particular movie.
	
	int k=0; //used as array pointer.


	while(flag1==1 || flag2==1)
	{
	//List of movies to choose from
    cout<<"Enter movie you want to watch "<<endl;
	cout<<"1.Terminator"<<endl;
    cout<<"2.The Matrix"<<endl;
	cout<<"3.Inception"<<endl;
	cout<<"4.The Lion King"<<endl;
	cout<<"5.Fast and Furious"<<endl;
	cout<<"6.Back To The Future"<<endl;
	cout<<"7.Rocky"<<endl;
	cout<<"8.Indiana Jones"<<endl;
	cout<<"9.Pulp Fiction"<<endl;
	cin>>movie_num;
	cout<<"Enter Number of tickets you want to book"<<endl;
	cin>>num_ticket;
	
	
	if(num_ticket>tickets_left[movie_num-1])//if tickets are remaining
	{
		cout<<"Sorry "<<num_ticket<<" tickets not available choose another movie"<<endl;
		flag2=1;
	}
	else
	{
	flag2=0;
	while(k<num_ticket)//while all tickets are being booked
	{
    cout<<"Please type in name of person "<<k+1<<endl;;
	cin>>name[k];
	cout<<"Please type in age of person: "<<k+1<<endl;
	cin>>age[k];
	
	     
		 if(age_rating[movie_num-1] >age[k])
		{
		
		cout<<"Sorry, You're under-aged, please choose another movie."<<endl;
		flag1=1;
	}
	else
	{
		//for various time slots.
		flag1=0;
		cout<<"Please Enter the time"<<endl;
		cout<<"1->9:45am"<<endl;
		cout<<"2->12:00pm"<<endl;
		cout<<"3->3:30pm"<<endl;
		cout<<"4->6:20pm"<<endl;
		cout<<"5->9:00pm"<<endl;
		cin>>time_number;
		cout<<"Thank You for booking "<<movie_name[movie_num-1]<<endl;
     
	} // end of else statement
	k++;//increment k
	 }// end of 2nd while loop
	 
   }//end of first else loop.
	
  }//end of first while loop.
  tickets_left[movie_num-1]-=num_ticket;//reducing the number of tickets in the array.
  

}//end of function.

void customer_details::display_details()
{
	ofstream fout;//write into a file.
	
	fout.open("Tickets.txt");//opening and create a file.
	
	for(int i=0;i<num_ticket;++i)
{
	//writing details of customers in the file.
	
	fout<<"Name: "<<name[i]<<"\n";
	fout<<"Age: "<<age[i]<<"\n";
	fout<<"Movie: "<<movie_name[movie_num-1]<<"\n";
	fout<<"Time: "<<time[time_number-1]<<"\n";
} //end of loop
	fout<<"Thanks for Booking!"<<"\n"; 
    fout.close();  //close the file
}//end of function.

int main()
{
	int again='y';// if customer wants to book more movies.
	
	while(again=='y' || again=='Y')
	{
	customer_details cd; //customer_details object
	cd.enter_details();
	
	cd.display_details();
	cout<<"Do you want to book another movie? 'y' or 'Y' -> yes others no "<<endl;
	cin>>again;
  } //end of while loop
}//end of function

/***************************************************************************************************************************************************************/
