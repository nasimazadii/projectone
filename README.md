# projectone
/*
 * pjone.c
 *
 *  Created on: Feb 27, 2019
 *      Author: Nasim Azadi
 */


#include <stdio.h>
/*
 * pjone.c
 *
 *  Created on: Feb 26, 2019
 *      Author: Nasim Azadi
 */
int main()
{
	// fflush("stream");
	int seat[15][30];
	double seatPrice[15][30];
	char seatDemo[15][30];
	int seatsold=0;
	//flush (stdin);
	printf("print prices for each seat: ");
	for(int i=0;i<15;i++)
	{
		int j=0;
		while(j<30)
		{double a;
			do
		{
			printf("enter the price of seat at row %d, column %d: ",(i+1),(j+1));
			scanf("%f",&a);
		}while(a<0);
			seatPrice[i][j]=a;
			j=j+1;

		}
		}
	// default elements of the arrays.
	for(int i=0;i<15;i++)
	{
		for(int j=0;j<15;j++)
		{
			seat[i][j]=1; // 1 indicates available seat
			seatDemo[i][j]= '#';
		}
	}
	void sellseat(int i,int j)
	{
		if(!(i>0 && i<16 && j>0 && j<31))
			printf("invalid input, try again.");
		else if(seat[i-1][j-1]==0)
			printf("Sorry.  This seat has already been sold. Try another one.");
		else
		{
			printf("The price for this seat is $%f \n",seatPrice[i-1][j-1]);
			printf("Do you want it? (answer 'y' for yes, and 'n' for no.)");
			//fflush(stdio);
			char b;
			scanf("%c",&b);
			switch(b)
			{
			case('y'):case('Y'):
	           {
				seat[i-1][j-1]=1;
					seatsold++;
					seatDemo[i-1][j-1]='*';
					displayState(); // will be defined...

	              }

			break;
			case('n'):case('N'):
					seat[i-1][j-1]=0;
			break;

			default:
				printf("Wrong. Try again. ('y' for yes, and 'n' for no.");

			}
		}
		void displayState()
		{
			printf("The total number of tickets sold is %d",seatsold);
			seatChart();
		}
		void seatChart()
		{
			printf("\t\t Seats \n");
			for(int i=0; i<15; i++)
			{
				for(int j=0;j<30; j++)
				{
					if(i==0)
						printf("Row 1\t");
					if(j<29)
						printf("%c", seatDemo[i][j]);
					else if(i!= 14)
						printf("%c \n Row %d\t",seatDemo[i,j],(i+2));
					else
						printf("%c", seatDemo[i][j]);
				}
			}

			int numberticketsSold()
			{
				return seatsold;

			}

			void ticketsInfo()
			{
				int totalsold = numberticketsSold();

				for(int k =0;k<15;k++)
				{
					int soldinRow= numberticketssold(i);
					printf("The number of tickets available in Row %d is %d \n",i,(30-soldinRow));
					printf("The number of tickets available in the whole stadium is %d\n",(450-totalsold));
				}
			}

			int numberticketssold(int i)
			{
				int sum =0;
				for(int j;j<30;j++)
					sum += seat[i][j];
				return sum;
			}

		}
	}
	return 0;
}

