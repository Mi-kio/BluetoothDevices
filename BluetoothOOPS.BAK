/* Question-

   (press "Page down" twice to skip reading this)

   When we turn on the Bluetooth we can access to connect to other phone
   but not access to call or send sms from that phone ,that level is hidden
   from encapsulation(some abstraction is available).


   The program includes the following OOP features
   1. Use of classes and Objects
   2. Encapsulation
   3. Data Abstraction
   4. Inheritance(single level and multiple inheritance)

   It contains 5 classes

1. BluetoothAdapter
   For turning on/off bluetooth

2. Bluetooth Device
   Check connection of bluetooth and device info.

3. Device 2
   This class is made for client device
   The bluetooth of client device is assumed to be on and it accept all
   the file tranferred by server/master device.

4. BluetoothSocket
   Makes Connection, finds device

5. BluetoothServerSocket
   This class encloses the bluetooth profile which permit or deny for calls
   and sms.

# Program shows how making calls and sending sms are restricted when
  2 phones are in a bluetooth connection.It lacks some features
   due to which it don't shows exact working of a bluetooth.
*/


#include<iostream.h>
#include<conio.h>
#include<string.h>
#include<stdio.h>
#include<graphics.h>


int n=0;             //global variable
class BluetoothAdapter
{
public:
	int i;
	static int S;
	static int State;
	int Action_request_Enable;

public:
    static int support()
    {
    static int S=1;
    if(S==1)
    {
    ;
    }
    return S;
    }

    BluetoothAdapter()
    {
    if(support()==1)
    {
   ;
    }
    else
    {
    cout<<"Device don't supports"<<endl;
    State=0;
    }
    }

protected:
     int state()
    {
    if(support()==1)
    {
    char ch;
    cout<<endl;
    cout<<"Enable bluetooth?\n";
    cout<<"Click Y/y for enabling"<<endl;
    cin>>ch;

    if(ch=='y' || ch=='Y')
    {
    State=1;
    }
    else
    State=0;
    }
    else
    State=0;
    return State;
    }


public:
    int isEnabled(int ARE,int k)
    {
    State=k;
    if(support()==1)
    {
     if(ARE==1 && State==1)
     {
     cout<<"Bluetooth Enabled"<<endl;
     cout<<endl;
     i=1;
     }
     else if(state()==1)
     {
      cout<<"Bluetooth enabled"<<endl;
     i=1;
    }

     else
    {
     cout<<"Bluetooth disabled\n";
     StartActivityForResult();
     i=-1;
    }
     }
     else
     cout<<"disabled"<<endl;
     return i;
     }


  private:
     int StartActivityForResult()
     {
      char a[7]={'A','c','c','e','p','t'};
      char str[7];
      puts("Enable Bluetooth??\n");
      cout<<endl;
      puts("Accept                                     Deny\n");
      gets(str);

      if(strcmp(str,a)==0)
     {
      cout<<"Enabling"<<endl;

      cout<<"............................"<<endl;
      cout<<endl;
      Action_request_Enable=1;
      State=1;
      isEnabled(Action_request_Enable,State);
     }
      else
   {
      close();
   }
      return i;
      }


public:
  int showState()
  {
	return State;
  }

  protected:
	 int close()
	{
	 clrscr();
	 State=0;
	 cout<<"Turning off bluetooth"<<endl;
	 return State;
	 getch();
	}
};


class BluetoothDevice: public BluetoothAdapter
{
public:

   char name[20];
   int class1,c;//one(100m), two(10m) or three(1 meter) or four (-0.5 m)
   //random static address
 protected: static char BD_ADDR[48];
  // uniquely identifies device
  //(Bluetooth Unique address)

public:
  int check()
  {
  if(showState()==1)
  {
  c=1;
  }
  else
  c=-1;
  return c;
  }


     BluetoothDevice()
     {
       if(check()==1)
       {
	State=1;
	strcpy(name,"D_one");

       class1=2;
       }
  }
  };


class Device2
 {
//assume this device has turned on bluetooth
//open to network
//acts as client only
//slave device
public: int TurnOn;
    static char Dname[20];
	int class2;
	int accept;
	int pairCode;
   static  char Dtype[30];
protected:  static char BD_ADDR_2[48];
public:
int open()
{
 TurnOn=1;

return TurnOn;
}
public:
int About()
{
 class2=2;
 return 1;
}
protected:
int acceptRequest()
{
 accept=1;
 return accept;
}
protected:
int code()
{
pairCode=3491;
return pairCode;
}
 };


class BluetoothSocket: public Device2, protected  BluetoothDevice
{
public: int chc;
      static int p;
private:
int ConnectAs()
{

  if(check()==1)
{
cout<<endl;
cout<<endl;
 cout<<"For connecting as server press 1 and for client press 2"<<endl;
 cin>>chc;
 if(chc==1)
   p=1;
 else if(chc==2)
 {
  p=2;
 }
else
 close();
}
 return p;
}
public:
int ConnectingAs()
{

  if(check()==1)
{
 if(ConnectAs()==1)
 {
  p=1;
 }
// else if(ConnectingAs()==2)
else
 {
 cout<<"Wait for server"<<endl;
// close();
 p=0;
 }
}
return p;
}

// 1 Find device
// 2 Query paired device
// 3 Discover device
// 4 Connect Devices
// 5 Connect as client or server,,,, ( ask and proceed )
//separate classes for client and server


public: int i;
protected:
  int FindDevice()
{
 clrscr();
 cout<<endl;
 cout<<endl;
   if(check()==1)
   {   gotoxy(20,41);
       if(n==0)
       cout<<"No previously connected devices found"<<endl;
       puts("Looking for a device to connect\n");
       getch();
       gotoxy(25,42);
       puts("...............................................................................\n");
       getch();
       puts("................................................................................\n");
       gotoxy(30,12);
       cout<<"....................."<<endl;
       getch();
       if(open()==1)
       {
	 clrscr();
	 cout<<endl;
	 cout<<"Found a device "<<Dname<<endl;

	 i=1;
       }
   }
   return i;

}

int GetBondedDevice()
{
 if(n==0)
 {
 cout<<endl;
 cout<<"Share your first file using bluetooth";
 cout<<endl;
 }
 return n;
}

public:
int DiscoverDevice()
{

 int y,reply;
 if(ConnectingAs()==1)
 {
if(check()==1)
{
  if(FindDevice()==1)
  {
    GetBondedDevice();
    cout<<endl;
    cout<<"Press 1 for connecting to "<<Dname<<endl;
    cout<<endl;
    cout<<endl;
    cin>>y;
    if(y==1)
    {
    cout<<endl;
     cout<<"Connection Request Sent.."<<endl<<endl;
/*     gotoxy(30,12);
     cout<<"......................."<<endl;
     getch();    */

     if(acceptRequest()==1)
     {
     cout<<endl;
     cout<<"Connected successfully with "<<Dname<<endl;
//       if(reply==1)
 //      cout<<BD_ADDR_2<<endl;
       n++;   //first device to be connected
     }
    }
    else
    {
    cout<<"Aborting operations"<<endl;
    close();
    }

    }
}
}
    return y;
    }


};


 class BluetoothServerSocket :private BluetoothDevice, private Device2
  {
 public: int chk;
	 char loc[100];
private:
	int A2DP; //Advanced audio distribution Profile
	int AVRCP; //Audio video remote control profile
       int SAP,MAP; //SIM access profiles and message access profile
       int PBAP; //phone book access profile
       int OPP; //Object push profile
       int OBEX; //Object exchange over logical link control and Adaptation protocol
       int HFP,HSP; //headset profiles
       int HDF; //Health device profile
       int SPP; //serial port profile  for pairing
       int DIP; //device Id profile
       int BIP;    //basic imaging profile
       int GAVDP; //general audio video distribution profile
       int VDP;  //Video distribute profile
       int GOEP; //Generic object exchange profile
       int FTP;  //file transfer profile
       int PAN;   //personal area network
       int CIP;   //common ISDN profile
       int CTP;     //cordless telephony profile
       int DUN;    //dial up network


private:    int clk;
   int g;

  void Function()
{
	 A2DP=1;
	 AVRCP=1;
	 BIP=1;
	 GAVDP=1;
	 GOEP=1;
	 VDP=1;
	 FTP=1;
	 PAN=1;
	 CIP=1;
	 DUN=1;
	 CTP=0;
	SAP=0,MAP=0;
	PBAP=0;
	OPP=1;
	OBEX=1;
	HFP,HSP=1;
	HDF=1;
	SPP=1;
	DIP=0;

}
public:
 int see()
 {

   if(check()==1)
   {
   match();
   }
   return 1;
   }

  public:
       int match()
       {


	if(strcmpi(Dtype,"Mobile")==0)
	{
	    chk=1;
	 Abstract(g);
	}


	 return chk;
       }

  private:
      int Abstract(int g)
  {
      clrscr();
      int num;

    int get;
  cout<<"Enter the number corresponding to media type"<<endl;
  cout<<"1. Images"<<endl;
  cout<<"2. Audio files"<<endl;
  cout<<"3. Video files"<<endl;
  cout<<"4. Documents(.txt, .ppt, .html etc)"<<endl;
  cout<<"5. Tethering"<<endl;
  cout<<"6. Request SMS access"<<endl;
  cout<<"7. Request call access"<<endl;
  cin>>get;

  switch(get)
 {
   case 1:
	   sendMedia();  //image
	   break;
   case 2:
	   sendMedia1();      //audio
	   break;
   case 3: sendMedia2(); //video
	   break;
   case 4: sendMedia3();  //docs
	   break;
   case 5: sendMedia4(); //tether
	   break;
   case 6: sendMedia5();      //sms
	   break;
   case 7: sendMedia6();  //calls
	   break;
  default: cout<<"Turning off"<<endl;
	   close();

 }
 return 1;
 }

private:
  int sendMedia( )  //image
  {
     Function();
     cout<<"Write the location from where to select the files\n"<<endl;
	   gets(loc);
     if(OPP==1 && OBEX==1 && BIP==1)
     {
      cout<<"Sending......"<<endl;
       if(acceptRequest()==1)
      {
	cout<<"Sent file"<<endl;
       cout<<"1 succesful, 0 Unsuccessful "<<endl;
	   cout<<"For sharing more  click 5"<<endl;
       cin>>clk;
       if(clk==5)
       Abstract(g);
       else
       close();

      }

     }

    return 1;
}
private:
  int sendMedia1()    //audio
  {
     Function();
   int dgt;
abc:     cout<<"Write the location from where to select the files\n"<<endl;
	   gets(loc);
     if(A2DP==1 && AVRCP==1)
     {
      cout<<"Sending......"<<endl;
       if(acceptRequest()==1)
      {
	cout<<"Sent files"<<endl;
       cout<<"1 succesful, 0 Unsuccessful "<<endl;
	   cout<<"For sharing more  click 5"<<endl;
       cin>>clk;
       if(clk==5)
       Abstract(g);
       else
       close();

      }

     }

    return 1;
}

private:                          //video
  int sendMedia2( )
  {
   Function();
     cout<<"Write the location from where to select the files\n"<<endl<<endl;
	   gets(loc);
     if(GAVDP==1 && AVRCP==1 && OPP==1 && VDP==1)
     {
      cout<<"Sending......"<<endl<<endl;
       if(acceptRequest()==1)
      {
	 cout<<"Sent files"<<endl;
       cout<<"1 succesful, 0 Unsuccessful "<<endl;
	   cout<<"For sharing more  click 5"<<endl;
       cin>>clk;
       if(clk==5)
       Abstract(g);
       else
       close();
      }
     }

    return 1;
}
private:
  int sendMedia3()                       //.docx,.ppt,.exe etc(text docs)
  {
    Function();
     cout<<"Write the location from where to select the files\n"<<endl;
	   gets(loc);
     if(FTP==1 && GOEP==1 && OPP==1)
     {
      cout<<"Sending......"<<endl;
       if(acceptRequest()==1)
      {
	cout<<"Sent file"<<endl;
       cout<<"1 succesful, 0 Unsuccessful "<<endl;
	   cout<<"For sharing more  click 5"<<endl;
       cin>>clk;
	if(clk==5)
       Abstract(g);
       else
       close();
      }
     }

    return 1;
}
private:
  int sendMedia4()  //tether
{
     Function();
     if(g!=1)
{
     if(DUN==1 && CIP==1 && PAN==1)
      {
      cout<<"Turning On mobile data"<<endl;
       if(acceptRequest()==1)
	 {
       cout<<"Bluetooth Tethering turned on "<<endl;
       g=1;
       }
       cout<<"For more operations  click 5"<<endl;
       cin>>clk;
       if(clk==5)
       Abstract(g);
	 }
 }

      else
       cout<<"Already turned on"<<endl;


    return 1;
}

private:
  int sendMedia5( )     //sms
  {
	Function();
     if(SAP ==1 && MAP==1 && DIP==1)
     {
      cout<<"Wait for a moment......"<<endl;
       if(acceptRequest()==1)
      {
       cout<<"Permitted"<<endl;
       cout<<"Connected device can use for messaging"<<endl;
	   cout<<"For sharing more  click 5"<<endl;
       cin>>clk;
       if(clk==5)
       Abstract(g);
       else
       close();
      }
     }
  else
   cout<<"This file type can not be shared"<<endl;
   cout<<"Access denied"<<endl;
       cout<<"For sending more  click 5"<<endl;
       cin>>clk;
       if(clk==5)
       Abstract(g);
       else
       close();

    return 1;
}

private:
  int sendMedia6( )     //calls
  {

	    Function();
	    cout<<"Wait for a moment"<<endl;
     if(SAP==1 && PBAP==1 && DIP==1 && CTP==1 && CIP==1)
     {

       if(acceptRequest()==1)
      {
       cout<<"Permitted"<<endl;
	   cout<<"For sharing more  click 5"<<endl;
       cin>>clk;
       if(clk==5)
       Abstract(g);
       else
       close();
      }
     }
  else
   cout<<"Access Denied"<<endl;
       cout<<"For sharing more files  click 5"<<endl;
       cin>>clk;
       if(clk==5)
       Abstract(g);
       else
       close();

    return 1;
}

  };

  int BluetoothAdapter::S;
  int BluetoothAdapter::State;
  //MAC address
  char BluetoothDevice::BD_ADDR[48] = {'0','0',':','1','1',':','2','2',':','3','3',':','F','F',':','E','E',':','J','J',':','5','5'};
  int BluetoothSocket::p;
 char Device2:: BD_ADDR_2[]={'1','1',':','4','4',':','6','8',':','2','B',':','4','0',':','7','7',':','D','D',':','4','D'};
 char Device2::Dname[]={'D','2'};
 char Device2::Dtype[]={'M','o','b','i','l','e'};
  int main()
  {
    clrscr();
    int ARE,k;

    BluetoothAdapter A;       //first class
    A.isEnabled(ARE,k);
    A.showState();

    BluetoothDevice B;                     //second
    B.check();

    Device2 two;                        //(client) third
    two.open();
    two.About();

    BluetoothSocket S; //fourth
    S.DiscoverDevice();


 BluetoothServerSocket T;
  T.see();
  getch();
  return 0;
    }



/* DRAWBACKS
1. Absence of a data structure to save the connected device names
2. Limited number(1) of device availability for connecting
3. No pairing done
*/
