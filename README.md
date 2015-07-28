#include <stdio.h>
#include <string.h>

void baseConvertFunction(int baseConvertFrom, int baseConvertTo, char inputValue[20])
{
	int i, j, searchValue=1, searchArray[10], remainingValue[10], searchValue2=0;
	char returnedValue[20];
	
	int numberOfDigit = strlen(inputValue);
	int numberOfDigit2=numberOfDigit;
	
	
	for(i=0; i<=numberOfDigit; i++)
	{
		if((inputValue[i]>='A') && (inputValue[i]<='Z'))
		{
			switch(inputValue[i])
			{
				case 'A' :
					searchArray[i]=10;
				    break;	
				
				case 'B' :
				    searchArray[i]=11;
				    break;	 	
				
				case 'C' :
					searchArray[i]=12;
				    break;
				    
				case 'D' :
					searchArray[i]=13;
				    break;
				    
				case 'E' :
					searchArray[i]=14;
				    break;
				    
				case 'F' :
					searchArray[i]=15;
				    break;
				    
				case 'G' :
					searchArray[i]=16;
				    break;
				    
				case 'H' :
					searchArray[i]=17;
				    break;
				    
				case 'I' :
					searchArray[i]=18;
				    break;
				    
				case 'J' :
					searchArray[i]=19;
				    break;
				    
				case 'K' :
					searchArray[i]=20;
				    break;
				    
				case 'L' :
					searchArray[i]=21;
				    break;
				    
				case 'M' :
					searchArray[i]=22;
				    break;
				    
				case 'N' :
					searchArray[i]=23;
				    break;
				    
				case 'O' :
					searchArray[i]=24;
				    break;	
			}
		}
		else
		{
			searchArray[i]=inputValue[i]-'0';
		} 
	}
	
	for(i=0; i<numberOfDigit; i++)
	{
		for(j=1; j<numberOfDigit2; j++)
		{
			searchValue*=baseConvertFrom;
		}
		searchArray[i]*=searchValue;
	    searchValue=1;
	    numberOfDigit2--;
	}
	for(i=0; i<numberOfDigit; i++)
	{
		searchValue2+=searchArray[i];		
	}
	

	
	i=0;
	
	while(baseConvertTo<searchValue2)
	{
		remainingValue[i]=searchValue2%baseConvertTo;
		searchValue2=(searchValue2-remainingValue[i])/baseConvertTo;
		i++;
	}
	
	remainingValue[i]=searchValue2;
	searchValue=i;
	j=0;
	
	for(i=searchValue; i>=0; i--)
	{
		if (remainingValue[i]>=10)
		{
			switch(remainingValue[i])
			{
				case 10 :
					returnedValue[j]='A';
				    break;	
				
				case 11 :
				    returnedValue[j]='B';
				    break;	 	
				
				case 12 :
					returnedValue[j]='C';
				    break;
				    
				case 13 :
					returnedValue[j]='D';
				    break;
				    
				case 14 :
					returnedValue[j]='E';
				    break;
				    
				case 15 :
					returnedValue[j]='F';
				    break;
				    
				case 16 :
					returnedValue[j]='G';
				    break;
				    
				case 17 :
					returnedValue[j]='H';
				    break;
				    
				case 18 :
					returnedValue[j]='I';
				    break;
				    
				case 19 :
					returnedValue[j]='J';
				    break;
				    
				case 20 :
					returnedValue[j]='K';
				    break;
				    
				case 21 :
					returnedValue[j]='L';
				    break;
				    
				case 22 :
					returnedValue[j]='M';
				    break;
				    
				case 23 :
					returnedValue[j]='N';
				    break;
				    
				case 24 :
					returnedValue[j]='O';
				    break;	
		    }
		}
	
		else
		{
			returnedValue[j]=remainingValue[i]+'0';
		}
		
		j++;
		
	}
	
	printf("%s base %d is equal to %s base %d\n",inputValue,baseConvertFrom,returnedValue,baseConvertTo);
    
	return; 
}

int main()
{
	int baseConvertFrom, baseConvertTo, searchValue=1;
	char inputValue [20];
	
	while(searchValue>0)
	{
		while(searchValue>0)
		{
			printf("Enter a base value to convert from:");  scanf("%d",&baseConvertFrom);	
		    if(baseConvertFrom>=2 && baseConvertFrom<=25)
		    {
		    	break;
			}
			else if(baseConvertFrom==0)
			{
				break;
			}
    	    printf("Please enter between 2-25, if you want to terminate the program enter '0'(zero)\n");
		}
		
		if( baseConvertFrom==0 )
		{
			break;
		}
		
		while(searchValue>0)
		{
			printf("Enter a base value to convert to:");  scanf("%d",&baseConvertTo);
		   
		    if(baseConvertTo>=2 && baseConvertTo<=25)
		    {
		    	break;
			}
			else if(baseConvertTo==0)
			{
				break;
			}
			printf("Please enter between 2-25, if you want to terminate the program enter '0'(zero)\n");
		}
		if( baseConvertTo==0 )
		{
			break;
		}
		
		printf("Enter the value to convert:");  scanf("%s",&inputValue);
		
		baseConvertFunction(baseConvertFrom,baseConvertTo,inputValue);
	
	}
	
	printf("Terminated successfully.");

	return 0;
}
