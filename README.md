# pilgrimage_management_project
This project consists of pilgrimage tourism packages with all the daywise itinerary and package costs. Each person has bucket full of option to choose the respective packages and the day-night schedule including the packages costs.


#include <iostream>
#include <fstream>
#include<string.h>
using namespace std;

void login();
void signup();
void change();
void package();
int main()
{
    int c;
    cout<<"\t\t\t  _______________                                            \n\n\n";
    cout<<"\t\t\t (^^)  WELCOME TO THE LOGIN PAGE (^^)      \n\n\n";
    cout<<"\t\t\t ________________\n\n\n";
    cout<<"\t\t\t  **  LET US HELP YOU CHOOSE WITH: **        \n\n";
    cout<<"                                           \n\n";
    cout<<"\t|  press 1 to LOGIN           |"<<endl;
    cout<<"\t| press 2 to SIGNUP           |"<<endl;
    cout<<"\t| press 3 to CHANGE PASSWORD  |"<<endl;
    cout<<"\t| press 4 to CHOOSE PACKAGE   |"<<endl;
    cout<<"\n\t\t\t plese enter your choice :";
    cin>>c;
    cout<<endl;
    
    switch(c)
    {
        case 1:
        login();
        break;
 case 2:
        signup();
        break;
        
        case 3:
        change();
        break;
        
        case 4:
        package();
        break;
        
        case 5:
        cout<<"\t\t\t Thankyou! \n\n";
        break;
        
        default:
        system("cls");
        cout<<"\t\t\t please select from the option given above \n"<<endl;
        main();
        
    }
}

void login() {
    int count;
    string userId,password,id,pass;
    system("cls");
    cout<<"\t\t\t please enter the username and password :"<<endl;
    cout<<"\t\t\t USERNAME ";
      cin>>userId;
cout<<"\t\t\t PASSWORD ";
      cin>>password;
      
      ifstream input("records.txt");
      while(input>>id>>pass)
      {
          if(id==userId && pass==password)
          {
              count=1;
              system("cls");
              
          }
      }
      input.close();
   if(count==1)
   {
       cout<<userId<<"\n Your LOGIN is successful \n Thanks for logging in ! \n";
       
   }
   else{
       cout<<"\n LOGIN ERROR \n please check your username and password\n";
       main();
       
   }
}
void signup()
{
    string ruserId,rpassword,rid,rpass;
    system("cls");
    cout<<"\t\t\t Enter the username : ";
    cin>>ruserId;
    cout<<"\t\t\t Enter the password : ";
    cin>>rpassword;
    
    ofstream f1("records.txt", ios::app);
    f1<<ruserId<<' '<<rpassword<<endl;
    system("cls");
    cout<<"\n\t\t\t signup is successfull! \n";
    main();
    
}
void change()
{
    int option;
    system("cls");
    cout<<"\t\t\t You want change password? No worries \n";
    cout<<"press 1 to search your id by username "<<endl;
    cout<<"press 2 to go back to the main menu "<<endl;
    cout<<"\t\t\t Enter your choice :";
    cin>>option;
    switch(option)
    {
        case 1:
 {
            int count=0;
            string suserId,sId,spass;
            cout<<"\n\t\t\tEnter the username which you remembered :";
            cin>>suserId;
            ifstream f2("records.txt");
            while(f2>>sId>>spass)
            {
                if(sId==suserId)
                {
                    count=1;
                    
                }
            }
            f2.close();
            if(count==1)
            {
                cout<<"\n\n your account is found! \n";
                cout<<"\n\n your password is : "<<spass;
                main();
                
            }
            else{
                cout<<"\n\t sorry! your account is not found! \n";
                main();
                
            }
            break;
            
        }
        case 2:
        {
            main();
  }
    
        default:
    cout<<"\t\t\t wrong choice ! please try again"<<endl;
        change();
    } 
}  
    void package(){
    
        int choice;
        system("cls");
        cout<<"\t\t\t choose your package\n";
        cout<<"press 7 to choose package of CHARDHAM Yatra"<<endl;
        cout<<"press 8 to choose package of spreads colour in vrindavan"<<endl;
        cout<<"press 9 to choose package of HEAVEN haridwar"<<endl;
        cout<<"press 0 to choose package of varansi"<<endl;
        cout<<"press 6 to choose package of AYODHYA"<<endl;
        cout<<"press 5 to choose package of south"<<endl;
        cin>>choice;
        switch(choice){
            case 7:
            
            
            cout<<"package of CHARDHAM is 175000";
            break;
            case 8:
            cout<<"package of Vrindavan costs 39500";
            break;
            case 9:
            cout<<"package of Haridwar costs 15000";
            break;
            case 0:
            cout<<"package of Varanasi costs 35000 ";
            break;
            case 6:
            cout<<"package of Ayodhya costs 7000";
            break;
            case 5:
            cout<<"package of South costs 40000";
            break;
            default:
            cout<<"please choose the valid choice option";
            
        }
    }
