#include<bits/stdc++.h>
using namespace std;
 
class Store{
 
public:
void registerr1();
void loginn1();
void loginn2();
 
void login();
void reg_login();
void main_menu_customer();
void main_menu_dealer();
 
};
 
void Store :: registerr1()     // Registration for Customer
{
     string reg_user,reg_pass;
    system("cls");
    cout<<" ----------------- USER REGISTRATION -------------------"<<endl;
   cout<<"User Name: ";
   cin>>reg_user;
   cout<<"Password ";
   cin>>reg_pass;
 
   ofstream reg("Register1.txt",ios::app);
   reg<<reg_user<<" "<<reg_pass<<endl;
   system("cls");
   cout<<"Registration is successful"<<endl;
}
 
void Store::loginn1()       // Login for Customer
{
    int exist;
    string user, pass,u,p;
    cout<<" ----------------- USER LOGIN -------------------"<<endl;
    cout<<"User Name: ";
   cin>>user;
   cout<<"Password ";
   cin>>pass;
 
   ifstream check("Register1.txt");
 
   while(check>>u>>p)
   {
       if(u == user && p==pass)
       {
           exist=1;
       }
   }
 
   check.close();
   if(exist==1)
   {
       system("cls");
       cout<<"Successfully logged in"<<endl;
   }
   else
   {
       system("cls");
      cout<<"Please enter valid user name or password"<<endl;
       loginn1();
 
   }
 
}
 
void Store:: loginn2()    //Login for dealer
{
    int exist=0;
    string user, pass,u,p;
    cout<<" ----------------- DEALER LOGIN -------------------"<<endl;
    cout<<"User Name: ";
   cin>>user;
   cout<<"Password ";
   cin>>pass;
 
  if(user=="admin" && pass=="123")
  {
      exist=1;
  }
   if(exist==1)
   {
         system("cls");
       cout<<"Successfully logged in"<<endl;
   }
   else
   {
         system("cls");
      cout<<"Please enter valid user name or password"<<endl;
      loginn2();
   }
 
}
 
void Store:: login()
{
    cout<<"----------- LOGIN AS ---------------"<<endl;
    cout<<"1. Customer"<<endl;
    cout<<"2. Dealer"<<endl;
    cout<<"3. Exit"<<endl;
 
}
 
void Store:: reg_login()
{
    system("cls");
    cout<<"-------------- SELECT ---------------"<<endl;
    cout<<"1. Register"<<endl;
    cout<<"2. Login"<<endl;
 
}
void Store:: main_menu_customer()
{
 
    cout<<"--------------- MAIN MENU -----------------"<<endl;
    cout<<"1. View all products"<<endl;
    cout<<"2. Purchase product"<<endl;
    cout<<"3. Return a product"<<endl;
    cout<<"4. Exit"<<endl;
 
}
 
void Store:: main_menu_dealer()
{
 
    cout<<"--------------- MAIN MENU -----------------"<<endl;
    cout<<"1. Add product"<<endl;
    cout<<"2. Delete product"<<endl;
    cout<<"3. Display all products"<<endl;
    cout<<"4. Refill products"<<endl;
    cout<<"5. Exit"<<endl;
 
}
 
class item : public Store{
 
// Attributes of product
    string p_name;
    int quantity, p_id;
    float price;
 
    public:
   
 
    void purchase_product(); // For Customer's Menu
    void product_return();   // For Customer,s Menu
    void display();          // For Both menu
    void add();              // For Dealer's Menu
    void delete_product();   // For Dealer's Menu
    void product_refill();   // For Dealer's Menu
 
};
 
 
void item:: add()
{
   system("cls");
 
    cout<<"\n ------------------ Add New Product ------------------- "<<endl;
    cout<<"\nProduct Id : ";
    cin>>p_id;
    cout<<"\nProduct Name :";
    cin>>p_name;
    cout<<"\nQuantity of Product :";
    cin>>quantity;
    cout<<"\nPrice of Product :";
    cin>>price;
    ofstream file("Stock_database.txt",ios::out|ios::app);
    file<<" "<<p_id<<" "<<p_name<<" "<<quantity<<" "<<price<<endl;
    file.close();
 
}
 
void item:: display()
{
    system("cls");
 
cout<<"\n--------------Display All Products--------------";
ifstream dis("Stock_database.txt",ios::in);
if(!dis)
cout<<"\n\n File Opening Error...."<<endl;
else
{
cout<<"\n\nProduct ID\tProduct Name\tQuantity\tPrice "<<endl;
dis>>p_id>>p_name>>quantity>>price;
while(!dis.eof())
{
    cout<<p_id<<"           \t"<<p_name<<"    \t"<<quantity<<"          \t"<<price<<endl;
    dis>>p_id>>p_name>>quantity>>price;
}
 
}
dis.close();
}
void item:: purchase_product()
{
    system("cls");
    fstream file,file1;
 
   int p_idd,quant,count=0;
   
    cout<<"\n\t\tPurchase Product";
    file1.open("Product1.txt",ios::app|ios::out);
    file.open("Stock_database.txt",ios::in);
    if(!file)
    cout<<"\n File not available";
    else
    {
        cout<<"\nProduct ID : ";
        cin>>p_idd;
        cout<<"\nQuantity : ";
        cin>>quant;
        file>>p_id>>p_name>>quantity>>price;
        while(!file.eof())
        {
            if(p_id == p_idd)
            {
                system("cls");
                cout<<"Product purchased successfully !!"<<endl;
 
                quantity-=quant;
                 file1<<p_id<<" "<<p_name<<" "<<quantity<<" "<<price<<"\n";
                 
                count++;
                 
            }
            else{
            file1<<p_id<<" "<<p_name<<" "<<quantity<<" "<<price<<"\n";
       
            }
 
            file>>p_id>>p_name>>quantity>>price;
        }
        if(count==0)
        cout<<"\nProduct not available";
       
    }
 
    file.close();
    file1.close();
    remove("Stock_database.txt");
    rename("Product1.txt","Stock_database.txt");
 
 
}
 
 
 
 
 
void item:: delete_product()
{
     system("cls");
    fstream file,file1;
    int quantity,count=0;
   int p_idd;
    cout<<"\n\t\tDelete Product Record";
    file1.open("Product1.txt",ios::app|ios::out);
    file.open("Stock_database.txt",ios::in);
    if(!file)
    cout<<"\n File not available";
    else
    {
        cout<<"\nProduct ID : ";
        cin>>p_idd;
        file>>p_id>>p_name>>quantity>>price;
        while(!file.eof())
        {
            if(p_id == p_idd)
            {
                system("cls");
                cout<<"\nRecord is deleted";
                cout<<"\n One Product deleted successfully";
                count++;
            }
            else
            file1<<p_id<<" "<<p_name<<" "<<quantity<<" "<<price<<"\n";
 
            file>>p_id>>p_name>>quantity>>price;
        }
        if(count==0)
        cout<<"\nProduct ID not found";
    }
    file.close();
    file1.close();
    remove("Stock_database.txt");
    rename("Product1.txt","Stock_database.txt");
 
}
 
 
void item:: product_return()
{
    system("cls");
    fstream file,file1;
 
   int p_idd,quant,count=0;
    cout<<"\n ----------------------- Return Product ----------------------";
    file1.open("Product1.txt",ios::app|ios::out);
    file.open("Stock_database.txt",ios::in);
    if(!file)
    cout<<"\n File not available";
    else
    {
        cout<<"\nProduct ID : ";
        cin>>p_idd;
        cout<<"\nQuantity : ";
        cin>>quant;
        file>>p_id>>p_name>>quantity>>price;
        while(!file.eof())
        {
            if(p_id == p_idd)
            {
                system("cls");
                cout<<"Product is successfully returned !!"<<endl;
 
                quantity+=quant;
                 file1<<p_id<<" "<<p_name<<" "<<quantity<<" "<<price<<"\n";
                 count++;
 
            }
            else
            file1<<p_id<<" "<<p_name<<" "<<quantity<<" "<<price<<"\n";
 
            file>>p_id>>p_name>>quantity>>price;
        }
           if(count==0)
           {
               cout<<"Enter correct product ID"<<endl;
           }
    }
    file.close();
    file1.close();
    remove("Stock_database.txt");
    rename("Product1.txt","Stock_database.txt");
 
 
}
 
void item:: product_refill()
{
    fstream file,file1;
 
   int p_idd,quant;
    cout<<"\n ----------------------- Refill Product ----------------------";
    file1.open("Product1.txt",ios::app|ios::out);
    file.open("Stock_database.txt",ios::in);
    if(!file)
    cout<<"\n File not available";
    else
    {
        cout<<"\nProduct ID : ";
        cin>>p_idd;
        cout<<"\nQuantity : ";
        cin>>quant;
        file>>p_id>>p_name>>quantity>>price;
        while(!file.eof())
        {
            if(p_id == p_idd)
            {
                system("cls");
                cout<<"\nRecord is updates";
 
                quantity+=quant;
                 file1<<p_id<<" "<<p_name<<" "<<quantity<<" "<<price<<"\n";
 
            }
            else
            file1<<p_id<<" "<<p_name<<" "<<quantity<<" "<<price<<"\n";
 
            file>>p_id>>p_name>>quantity>>price;
        }
 
 
    }
    file.close();
    file1.close();
    remove("Stock_database.txt");
    rename("Product1.txt","Stock_database.txt");
 
 
}
 
 
int main()
{
    item a;
    int choice1, choice2,choice3;
    char x;
 
    p:
    a.login();
    cout<<"Enter your choice: "<<endl;
    cin>>choice1;
 
    switch(choice1)
    {
        case 1: a.reg_login();
                cout<<"Enter your choice: ";
                cin>>choice2;
                switch(choice2)
                {
                    case 1: a.registerr1();
                            break;
                    case 2: a.loginn1();
                            break;
                }
                z:
                a.main_menu_customer();
 
                cout<<"Enter your choice: ";
                cin>>choice3;
 
                switch(choice3)
                {
                    case 1: a.display();
                            break;
                    case 2: a.purchase_product();
                            break;
                    case 3: a.product_return();
                            break;
                    case 4: system("cls");
                            goto p;
                            break;
                    default: cout<<"Enter correct choice "<<endl;
                }
                goto z;
                break;
 
        case 2:
                a.loginn2();
 
                y:
                a.main_menu_dealer();
 
                cout<<"Enter your choice: ";
                cin>>choice3;
 
                switch(choice3)
                {
                    case 1:
                            do
                           {
                             a.add();
                            cout<<"\n\n Do you want to add another product (y,n) : ";
                            cin>>x;
                            } while (x=='y');
                            break;
                    case 2: a.delete_product();
                            break;
                    case 3: a.display();
                            break;
                    case 4: a.product_refill();       //For Refill
                            break;
                    case 5: system("cls");
                            goto p;
                            break;
 
                    default: cout<<"Enter correct choice "<<endl;
                }
 
                goto y;
                break;
 
        case 3:  exit(0);
                break;
 
        default: cout<<"This Choice is not avialable.... Please try again"<<endl;
 
    }
 
 
 
 
return 0;
}
