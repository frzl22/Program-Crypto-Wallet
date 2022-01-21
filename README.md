// Program-Crypto-Wallet
//program that slightly look a like crypto wallet
#include <iostream>
#include <conio.h>

using namespace std;

int main(int argc, char** argv) 
{
	struct identitas
	{
		int no_wallet;
		char first [20], last[30], city[40], j_t[20];
		long bal, depo, withdraw, t_w, t_d, transfer, terima, tw, td;
		float bunga;
	};
	int a=-1;
	identitas id[100];
	char jawab, lagi, pass[6];
	int n, t, input, menu, ma, mn;
	
		{
			menu:
			system("cls");
			m:
				cout<< "\nx===================================x";
				cout<< "\n                                     ";
				cout<< "\n     Crypto Wallet Registration      ";
				cout<< "\n                                     ";
				cout<< "\nx===================================x";
				cout<< "\n";
				cout<< "\n+-----------------------------------+";
				cout<< "\n1. Admin Menu                        ";
				cout<< "\n2. Costumer Menu                     ";
				cout<< "\n3. Exit                              ";
				cout<< "\n+-----------------------------------+";
				cout<< "\nPlease Choose a Menu 1/2/3 : ";
					cin>> menu;
		if(menu==1)
		{
			m_a:
			system("cls");
			asking:
				cout<< "\nx===================================x";
				cout<< "\n           Admin Menu                ";
				cout<< "\nx===================================x";
				cout<< "\n1. Input Costumer Data               ";
				cout<< "\n2. Costumer List                     ";
				cout<< "\n3. Withdrawal and Deposit Report     ";
				cout<< "\n4. Exit                              ";
				cout<< "\nx===================================x";
				cout<< "\n";
				cout<< "\nPlease Choose a menu 1/2/3/4 : ";
					cin>> ma;
		switch (ma)
		{
			case 1:
			{
				ma1:
				a++;
				system("cls");
					cout<< "\nx========================================x";
					cout<< "\n            Input Costumer Data           ";
					cout<< "\nx========================================x";
					cout<< "\n Wallet Number      : ";
						cin>> id[a].no_wallet;
					cout<< "\n First Name         : ";
						cin>> id[a].first;
					cout<< "\n Last Name          : ";
						cin>> id[a].last;
					cout<< "\n City Where you live : ";
						cin>> id[a].city;
					cout<< "\n Wallet Type (Worker, Student, CS(campus student)) : ";
						cin>> id[a].j_t;
					cout<< "\n";
					cout<< "\n+----------------------------------------+";
					cout<< "\n       Data Successfully Processed        ";
					cout<< "\n                                          ";
					cout<< "\n              Thank You!!                 ";
					cout<< "\n+----------------------------------------+";
			ask:
				cout<< "\nInput Next Costumer Data ? (y/n) \n";
					cin>> lagi;
						if(lagi=='y' ||lagi=='Y')
							{
								goto ma1;
							}
						else if(lagi=='n' ||lagi=='N')
							{
								goto m_a;
							}
						else
							{
								cout<< "\n That's Something Wrong!!";
									goto ask;
							}
					getch();
			}
			case 2:
			{
				ma2:
				system("cls");
					cout<< "\n+----------------------------------------+";
					cout<< "\n              List Costumer               ";
					cout<< "\n+----------------------------------------+";
				for(n=0;n<=a;n++)
				{
					cout<< "\nNo.            : "<< (n+1)<< endl;
					cout<< "\nWallet Number  : "<< id[n].no_wallet<< endl;
					cout<< "\nName           : "<< id[n].first<< " "<< id[n].last<< endl;
					cout<< "\n+----------------------------------------+";
				}
				ask1:
					cout<< "\nWanna See Detail Costumer ? (y/n) \n";
						cin>> jawab;
				if(jawab=='y' ||jawab=='Y')
					{
						nomo_rek:
							cout<< "\nInput Number of Wallet for Detail Costumer : ";
								cin>> input;
							for(n=0;n<=a;n++)
							{
								if (input==id[n].no_wallet)
							{
						system ("cls");
							cout<< "\n+----------------------------------------+";
							cout<< "\n        Detail Costumer Data              ";
							cout<< "\n+----------------------------------------+";
							cout<< "\n Wallet Number      : "<< id[n].no_wallet<< endl;
							cout<< "\n Name               : "<< id[n].first<< " "<< id[n].last<< endl;
							cout<< "\n City               : "<< id[n].city<< endl;
							cout<< "\n Type of Wallet     : "<< id[n].j_t<< endl;
							cout<< "\n Balance Amount     : "<< id[n].bal<< endl;
								id[n].bunga=id[n].bal*0.05;
										cout<< "interest (5%/month) : BTC"<< id[n].bunga<< endl;
										cout<< "\n+----------------------------------------+";
				ask2:
					cout<< "\nBack to list Costumer ? (y/n) \n";
						cin>> jawab;
					if(jawab=='y'|| jawab=='Y')
					{
						goto ma2;
					}
					else if(jawab=='n'|| jawab=='N')
					{
						goto m_a;
					}
					else
					{
						cout<< "\n+----------------------+";
						cout<< "\n  Wrong input Dudeee!!  ";
						cout<< "\n+----------------------+";
							goto ask2;
					}
						}
						}
						cout<< "\n Wrong Number Wallet Dudee!!";
							goto nomo_rek;
			}
				else if(jawab=='n'|| jawab=='N')
				{
					goto m_a;
				}
				else
				{
					cout<< "\n Wrong Input Dudeeee!!";
						goto ask1;
				}
			getch();
			}
			case 3:
			{
				system("cls");
					cout<< "\n+---------------------------------+";
					cout<< "\n   Withdrawal and Deposit Report   ";
					cout<< "\n+---------------------------------+";
					cout<< "\n";
				for(n=0;n<=a;n++)
				{
					cout<< "\n+---------------------------------+";
					cout<< "\n Number           : "<< (n+1)<< endl;
					cout<< "\n Wallet Number    : "<< id[n].no_wallet<< endl;
					cout<< "\n Name             : "<< id[n].first<< " "<< id[n].last<< endl;
					cout<< "\n Total Deposit    : "<< id[n].t_d<< endl;
					cout<< "\n Total Withdrawal : "<< id[n].t_w<< endl;
					cout<< "\n Total Cashback   : "<< id[n].tw<< endl;
					cout<< "\n Total Transfer   : "<< id[n].td<< endl;
						id[n].bunga=id[n].bal*0.05;
								cout<< "interest (5%/month) : BTC"<< id[n].bunga<< endl;
								cout<< "Remaining Balance   : BTC"<< id[n].bal<< endl;
								cout<< "\n";
								cout<< "\n+---------------------------------+";
				}
			print:
				cout<< "\nPrint Progress ? (y/n) \n";
					cin>> jawab;
					{
						if(jawab=='y'|| jawab=='Y')
						{
							system("cls");
								for(n=0;n<=a;n++)
								{
									cout<< "\n+-----------------------------------------------------+\n";
									cout<< " Number              : "<< (n+1)<< endl;
									cout<< " Wallet Number       : "<< id[n].no_wallet<< endl;
									cout<< " Name                : "<< id[n].first<< " "<< id[n].last<< endl;
									cout<< " City                : "<< id[n].city<< endl;
									cout<< " Total Deposit       : "<< id[n].t_d<< endl;
									cout<< " Total Withdrawal    : "<< id[n].t_w<< endl;
									cout<< " Total Transfer      : "<< id[n].td<< endl;
									cout<< " Total Receive       : "<< id[n].tw<< endl;
									cout<< " Interest (5%/month) : "<< id[n].bunga<< endl;
									cout<< " Remaining Balance   : "<< id[n].bal<< endl;
									cout<< "\n";
									cout<< "\n+-----------------------------------------------------+";
								}
						}
						else if(jawab=='n'|| jawab=='N')
						{
							goto m_a;
						}
						else
						{
							cout<< "\nWrong Input Dudeeee!!";
								goto print;
						}
					}
			asking1:
				cout<< "\nDescription : ";
				cout<< "\n(y/Y) = For back to the Admin Menu";
				cout<< "\n(n/N) = For back to the Main Menu";
				cout<< "\nBack to Admin menu ? (y/n) \n";
					cin>> jawab;
						if(jawab=='y'|| jawab=='Y')
						{
							goto m_a;
						}
						else if(jawab=='n'|| jawab=='N')
						{
							goto menu;
						}
						else
						{
							cout<< "\n There is something wrong!!";
								goto asking1;
						}
					getch();
			}
			case 4:
			{
				goto menu;
					getch();
			}
				default:
					cout<< "\n The Selected menu doesn't exist!!";
						goto asking;
				getch();
		}
		getch();	
		}
	if(menu==2)
	{
		system("cls");
		awal:
			cout<< "\n Input Wallet Number : ";
				cin>> input;
			for(n=0;n<=a;n++)
			{
				if(input==id[n].no_wallet)
				{
					m_n:
					system("cls");
					mn:
						cout<< "\n+----------------------------------------+";
						cout<< "\n              Costumer Menu               ";
						cout<< "\n+----------------------------------------+";
						cout<< "\n 1. Deposit                               ";
						cout<< "\n 2. Withdrawal                            ";
						cout<< "\n 3. Transfer                              ";
						cout<< "\n 4. Check Balance                         ";
						cout<< "\n 5. Exit                                  ";
						cout<< "\n+----------------------------------------+";
						cout<< "\n";
						cout<< "\n Please Choose a Menu 1/2/3/4/5 : ";
							cin>> mn;
		switch(mn)
		{
			case 1:
				{
					system("cls");
						cout<< "\n+--------------------------+";
						cout<< "\n          Deposit           ";
						cout<< "\n+--------------------------+";
						cout<< "\n";
							{
								{
									cout<< "\n+--------------------------------+";
									cout<< "\n        Detail Costumer Data      ";
									cout<< "\n+--------------------------------+";
									cout<< "\n Wallet Number    : "<< id[n].no_wallet<< endl;
									cout<< " Name              : "<< id[n].first<< " "<< id[n].last<< endl;
									cout<< " City              : "<< id[n].city<< endl;
									cout<< " Wallet Type       : "<< id[n].j_t<< endl;
									cout<< " Balance amount    : BTC"<< id[n].bal<< endl;
									cout<< "\n";
									cout<< " Input Amount You want to Deposit : BTC";
										cin>> id[n].depo;
									cout<< "\n";
										{
											if(id[n].depo<100000)
												{
													system("cls");
														cout<< "\n+-------------------------------------------------+";
														cout<< "\n  Sorry the Deposit can't we process at this time  ";
														cout<< "\n                                                   ";
														cout<< "\n            Minimum Deposit 100000BTC              ";
														cout<< "\n+-------------------------------------------------+";
												}
											else
												{
													id[n].bal=id[n].depo+id[n].bal;
													id[n].t_d=id[n].depo+id[n].t_d;
													system("cls");
														cout<< "\n+------------------------------+";
														cout<< "\n Deposit Successfully processed ";
														cout<< "\n+------------------------------+";
														cout<< "\n";
														cout<< "\n Your Amount Balance : BTC"<< id[n].bal;
														cout<< "\n";
												}
										}
								}
							}
			asking2:
				cout<< "\n (y/Y) = For Back to Costumer Menu";
				cout<< "\n (n/N) = Fot Back to Main Menu";
				cout<< "\nBack to Costumer Menu ? (y/n) \n";
					cin>> jawab;
						if(jawab=='y'|| jawab=='Y')
						{
							goto m_n;
						}
						if(jawab=='n'|| jawab=='N')
						{
							goto menu;
						}
						else
						{
							cout<< "\n There is something wronggg duuude!!";
								goto asking2;
						}
					getch();
				}
			case 2:
				{
					system("cls");
						cout<< "\n+-------------------------------------+";
						cout<< "\n               withdrawal              ";
						cout<< "\n+-------------------------------------+";
						cout<< "\n";
						{
							{
								cout<< "\n+-------------------------------------+";
								cout<< "\n         Detail Costumer Data          ";
								cout<< "\n+-------------------------------------+";
								cout<< "\n Wallet Number       : "<< id[n].no_wallet<< endl;
								cout<< "\n Name                : "<< id[n].first<< " "<< id[n].last;
								cout<< "\n City                : "<< id[n].city<< endl;
								cout<< "\n Wallet Type         : "<< id[n].j_t<< endl;
								cout<< "\n Remaining Balance   : "<< id[n].bal<< endl;
								cout<< "\n";
								cout<< "\n Input Amount You want to Withdraw : BTC";
									cin>> id[n].withdraw;
								cout<< "\n";
									if(id[n].bal-id[n].withdraw<500000)
										{
											system("cls");
												cout<< "\n+---------------------------------------+";
												cout<< "\n Sorry Your amount balance is not enough ";
												cout<< "\n    Minimum amount Withdraw 500000BTC    ";
												cout<< "\n+---------------------------------------+";
										}
									else
										{
											id[n].bal=id[n].bal-id[n].withdraw;
											id[n].t_d=id[n].withdraw+id[n].t_w;
											system("cls");
												cout<< "\n+---------------------------------------+";
												cout<< "\n     Withdrawal Succesfully Processed    ";
												cout<< "\n    Please Check on Your Bank Account    ";
												cout<< "\n+---------------------------------------+";
												cout<< "\n";
												cout<< "\n Remaining Balance : BTC"<< id[n].bal;
												cout<< "\n"<< endl;
										}
								}
							}
			asking3:
				cout<< "\n (y/Y) = For Back to Costumer Menu";
				cout<< "\n (n/N) = For Back to Main Menu";
				cout<< "\n Back to Costumer Menu ? (y/n) \n";
					cin>> jawab;
				if(jawab=='y'|| jawab=='Y')
				{
					goto m_n;
				}
				if(jawab=='n'|| jawab=='N')
				{
					goto menu;
				}
				else
				{
					cout<< "\n There is something wrong dude!!";
						goto asking3;
				}
			getch();
				}
			case 3:
				{
					system("cls");
						cout<< "\n+-------------------------------------+";
						cout<< "\n                Transfer               ";
						cout<< "\n+-------------------------------------+";
							mn4:
								cout<< "\n Input Wallet Number You want to Transfer : BTC";
									cin>> input;
										for(t=0;t<=a;t++)
											{
												if(input==id[t].no_wallet)
												{
													cout<< "\n+-------------------------------------+";
													cout<< "\n Wallet Number   : "<< id[t].no_wallet<< endl;
													cout<< " Name             : "<< id[t].first<< " "<< id[t].last<< endl;
													cout<< " City             : "<< id[t].city<< endl;
													cout<< " Input Amount you want to Transfer : BTC";
														cin>> id[t].transfer;
			asking5:
				cout<< "\n Is this the right data ?";
				cout<< "\n Process  Transfer ? (y/n) \n";
					cin>> jawab;
						if(jawab=='y'|| jawab=='Y')
						{
							if(id[n].bal-id[t].transfer<200000)
							{
								system("cls");
									cout<< "\n+-------------------------------------+";
									cout<< "\n   Sorry Your Balance are not enough   ";
									cout<< "\n   Minimum Balance Amount 200000BTC    ";
									cout<< "\n+-------------------------------------+";
							}
						else
							{
								id[n].bal=id[n].bal-id[t].transfer;
								id[t].bal=id[t].transfer+id[t].bal;
								id[t].tw=id[t].transfer+id[t].tw;
								id[n].td=id[t].transfer+id[n].td;
									system("cls");
										cout<< "\n+-------------------------------------+";
										cout<< "\n    Transfer Successfully Processed    ";
										cout<< "\n              Thank You                ";
										cout<< "\n+-------------------------------------+";
										cout<< "\n Remaining Balance : BTC"<< id[n].bal<< endl;
							}
			asking7:
				cout<< "\n+-------------------------------------+";
				cout<< "\n Description =";
				cout<< "\n (y/Y) = For Back to Costumer Menu";
				cout<< "\n (n/N) = For Back to Main Menu";
				cout<< "\n Back to Costumer Menu ? (y/n)\n";
					cin>> jawab;
						if(jawab=='y'|| jawab||'Y')
						{
							goto m_n;
						}
						else if(jawab=='n'|| jawab=='N')
						{
							goto menu;
						}
						else
						{
							cout<< "\n There is Something wroooonggg dudee!!";
								goto asking7;
						}
						}
						else if(jawab=='n'|| jawab=='N')
						{
							goto mn4;
						}
						else
						{
							cout<< "\n There is something wroooongg dudee!!";
								goto asking5;
						}
											}
										}
							cout<< "\n Wallet Number Are not Registered!!";
			asking6:
				cout<< "\n Back to the menu ? (y/n) \n";
								cin>> jawab;
									if(jawab=='y'|| jawab=='Y')
									{
										goto m_n;
									}
									else if(jawab=='n'|| jawab=='N')
									{
										goto mn4;
									}
									else
									{
										cout<< "\n There is something wrong duuudee!!";
											goto asking6;
									}
								getch();
				}
				case 4:
					{
						system("cls");
							cout<< "\n+-------------------------------------+";
							cout<< "\n             Check Balance             ";
							cout<< "\n+-------------------------------------+";
								{
									{
										cout<< "\n+-------------------------------------+";
										cout<< "\n         Detail Costumer Data          ";
										cout<< "\n+-------------------------------------+";
										cout<< "\n";
										cout<< "Wallet Number          : "<< id[n].no_wallet<< endl;
										cout<< "Name                   : "<< id[n].first<< " "<< id[n].last<< endl;
										cout<< "City                   : "<< id[n].city<< endl;
										cout<< "Wallet Type            : "<< id[n].j_t<< endl;
									id[n].bunga=id[n].bal*0.05;
										cout<< "\n Interest (5%/month) : BTC"<< id[n].bunga<< endl;
										cout<< "\n Total Balance       : BTC"<< id[n].bal<< endl;
									}
								}
			asking4:
				cout<< "\n (y/Y) = For Back to Costumer Menu";
				cout<< "\n (n/N) = For Back to Main Menu";
				cout<< "\n Back to Main Menu ? (y/n) \n";
					cin>> jawab;
						if(jawab=='y'|| jawab=='Y')
						{
							goto m_n;
						}
						if(jawab=='n'|| jawab=='N')
						{
							goto menu;
						}
						else
						{
							cout<< "\n There is Someeething Wrongg Dudeeee!!";
								goto asking4;
						}
					getch();
					}
				case 5:
					{
						goto menu;
					}
						default:
							{
								cout<< "\n The Menu You Selected doesn't Existt!";
									goto mn;
							}
						getch();
		}
				}
			}
				cout<< "\n Wrong Number Wallet Dudee!!";
					goto awal;
	}
	else if(menu>3)
	{
		cout<< "\n The Menu You Selected doesn't Exist Dudeee!";
			goto m;
	}
	}
	return 0;
}
