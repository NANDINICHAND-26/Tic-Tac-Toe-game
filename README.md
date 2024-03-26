# Tic-Tac-Toe-game
Tic Tac Toe Game in C programming language
#include<stdio.h>
void check(char,char);
char a[9]={'1','2','3','4','5','6','7','8','9'};
void gameName()
{
	printf("\n\t\t\tTic Tac Game :\n");
}
void show()
{
	printf("\n\n\t\t\t---|---|---\n");
	printf("\t\t\t %c | %c | %c \n",a[0],a[1],a[2]);
	printf("\t\t\t---|---|---\n");
	printf("\t\t\t %c | %c | %c \n",a[3],a[4],a[5]);
	printf("\t\t\t---|---|---\n");
	printf("\t\t\t %c | %c | %c \n",a[6],a[7],a[8]);
	printf("\t\t\t---|---|---\n");
}
void inputSymbol()
{
	printf("\nplayer 1 symbol :X:");
	printf("\nplayer 2 symbol :0:\n");
}
void start()
{
	char pa;
	printf("\nEnter who will start this game : player 1 or player 2\n");
	scanf("%c",&pa);
}
int count=0;
void play()
{
	char p, s;
	printf("\nEnter position and symbol for the player : \n");
	fflush(stdin);
	scanf("%c",&p);
	scanf("%c",&s);
	scanf("%c",&s);
	count++;
	check(p,s);
}
void check(char P, char S)
{
	int i;
	for(i=0;i<=8;i++)
	{
		if(a[i]==P)
		{
			a[i]=S;
		}
	}
}
int end()
{
	if((a[0]=='x'&&a[1]=='x'&&a[2]=='x')||(a[0]=='X'&&a[3]=='X'&&a[3]=='X'&&a[6]=='X'))
		return(100);
	else if((a[0]=='0'&&a[1]=='0'&&a[2]=='0')||(a[0]=='0'&&a[3]=='0'&&a[6]=='0'))
		return(200);
	else if(a[1]=='X'&&a[4]=='X'&&a[7]=='X')
		return(100);
	else if(a[1]=='0'&&a[4]=='0'&&a[7]=='0')
		return(200);
	else if(a[2]=='X'&&a[5]=='X'&&a[8]=='X')
		return(100);
	else if(a[2]=='0'&&a[5]=='0'&&a[8]=='0')
		return(200);
	else if(a[3]=='X'&&a[4]=='X'&&a[5]=='X')
		return(100);
	else if(a[3]=='0'&&a[4]=='0'&&a[5]=='0')
		return(200);
	else if(a[2]=='X'&&a[4]=='X'&&a[6]=='X')
		return(100);
	else if(a[2]=='0'&&a[4]=='0'&&a[6]=='0')
		return(200);
	else if(a[6]=='X'&&a[7]=='X'&&a[8]=='X')
		return(100);
	else if(a[6]=='0'&&a[7]=='0'&&a[8]=='0')
		return(200);
	return(300);			
}
int main()
{
	int k;
	char ch;
	labell:
	gameName();
	show();
	inputSymbol();
	start();
	play();
	
	label:
	show();
	play();
	k=end();
	show();
	if(count<9)
	{
		if(k==100)
		{
			printf("\nPlayer 1 won");
			count=0;
		}
		else if(k==200)
		{
			printf("\nPlayer 2 won");
			count=0;
		}
		else if(k==200)
		{
			printf("\nPlayer 2 won");
			count=0;
		}
		else
			goto label;
	}
	else
	{
		printf("\nGame Draw : ");
		count=0;
	}
	printf("\nDo you want to continue : enter y for Yes and n for No : ");
	fflush(stdin);
	scanf("%c",&ch);
	if(ch=='y'||ch=='Y')
	{
		a[0]='1';
		a[1]='2';
		a[2]='3';
		a[3]='4';
		a[4]='5';
		a[5]='6';
		a[6]='7';
		a[7]='8';
		a[8]='9';
		goto labell;
	}
}
