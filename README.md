# cn



#include<stdio.h>
#include<string.h>
void main()
{
	char s[20];
	int i=0,count=0;
	printf("Enter the String ");
	scanf("%s",s);
	printf("Before Bit Stuffing \n");
	printf("%s",s);
	printf("\nBit Stuffing with 5 Consecutive 1's \n");
	printf("After Stuffing \n");
	for(i=0;i<strlen(s);i++)
	{
		if(s[i]=='1')
		{
			count++;
		}
		else
		count=0;
		printf("%c",s[i]);
		if(count==5)
		{
			printf("0");
			count=0;
		}
    }
}
...............................................................
#include<stdio.h>
#include<string.h>
void main()
{
	char s[250],res[250],flag[10];
	int i,j,k=0;
	printf("Enter the String ");
	scanf("%s",s);
	printf("Enter the flag Value \n");
	scanf("%s",flag);
	printf("Before Byte Stuffing\n");
	printf("%s",s);
	printf("\nAfter Byte Stuffing\n");
	for(i=0;i<strlen(flag);i++)
   {
	printf("%c",flag[i]);
   }
	for(i=0;i<strlen(s);i++)
	{
		if(s[i]=='0'&&s[i+1]=='1'&&s[i+2]=='1'&&s[i+3]=='1'&&s[i+4]=='1'&&s[i+5]=='1'&&s[i+6]=='1'&&s[i+7]=='0')
		{
			for(j=0;j<strlen(flag);j++)
			{
				res[k++]=flag[j];
			}
		}
	res[k++]=s[i];
}
for(i=0;i<k;i++)
{
	
	printf("%c",res[i]);
}
for(i=0;i<strlen(flag);i++)
{
	printf("%c",flag[i]);
}
}

................................................................

#include<stdio.h>
#include<conio.h>
#include<math.h>
void hamming();
int main()
{

 int k,r,sum;
 printf("\nEnter the number of data bits and parity bits: ");
 scanf("%d%d", &k, &r);
 sum=k+r+1;
 if(sum<=pow(2,r))
 {
  printf("\nHamming code can be generated!!\n");
  hamming();
 }
 else
  printf("\nHamming code cannot be generated!!");
}
void hamming()
 {
    int data[12],datarec[12];
    int c1,c2,c4,c8,c,i;
    printf("Enter 8 bits of data one by one\n");
    for(i=1;i<=12;i++)
    {
    if((i==1)||(i==2)||(i==4)||(i==8))
    {

    }
else
scanf("%d",&data[i]);
   }

    data[1]=data[3]^data[5]^data[7]^data[9]^data[11];
data[2]=data[3]^data[6]^data[7]^data[10]^data[11];
data[4]=data[5]^data[6]^data[7]^data[12];
data[8]=data[9]^data[10]^data[11]^data[12];


printf("\nEncoded data is\n");
for(i=1;i<=12;i++)
{

     printf("%d \n",data[i]);

}
printf("Enter the Received data bits \n");
for(i=1;i<=12;i++)
{

     scanf("%d",&datarec[i]);

}

    c1=datarec[1]^datarec[3]^datarec[5]^datarec[7]^datarec[9]^datarec[11];
    c2=datarec[2]^datarec[3]^datarec[6]^datarec[7]^datarec[10]^data[11];
    c4=datarec[4]^datarec[5]^datarec[6]^datarec[7]^datarec[12];
    c8=datarec[8]^datarec[9]^datarec[10]^datarec[11]^datarec[12];
printf("Parity Checking Bits are %d%d%d%d",c8,c4,c2,c1);
c=c8*8+c4*4+c2*2+c1;
if(c==0)
{
printf("\nNo error while transmission of data\n");
}
else {
printf("\nError on position %d",c);
printf(" \n Correct Message \n");
if(datarec[c]==0)
{
datarec[c]=1;
    }
else
{
      datarec[c]=0;
}
for(i=1;i<=12;i++)
printf("%d",datarec[i]);

}
}
..................................................................

#include<stdio.h>
void main()
{
int i,j,a[30],b[20],m,n,q[20],r[20],temp,t[30];
printf("Enter m number of bits ");
scanf("%d",&m);
printf("Enter dividend data word\n");
for(i=0;i<m;i++)
{
scanf("%d",&a[i]);
}
printf("enter n no bits reqired for divisor \n");
scanf("%d",&n);
printf("enter divisor");
for(i=0;i<n;i++)
{
scanf("%d",&b[i]);
}
printf("by adding zeros at end of dividend");
for(i=m;i<(m+n);i++)
{
a[i]=0;
}
for(i=0;i<m;i++)
{
temp=i;
if(a[i]==1)
{
for(j=0;j<n;j++)
{
if(a[temp]==b[j])
{
a[temp]=0;
r[j]=0;
}
else
{
a[temp]=1;
r[j]=1;
}
temp=temp+1;
}
q[i]=1;
}
else
{
q[i]=0;
}
}
printf("the quotient is\n");
for(i=0;i<m;i++)
{
printf("%d",q[i]);
}
printf("the  remainder is\n");
for(i=1;i<n;i++)
{
printf("%d",r[i]);
}
printf("Enter the trasmitted data");
for(i=0;i<(m+(n-1));i++)
{
scanf("%d",&a[i]);
}
for(i=0;i<m;i++)
{
temp=i;
if(a[i]==1)
{
for(j=0;j<n;j++)
{
if(a[temp]==b[j])
{
a[temp]=0;
r[j]=0;
}
else
{
a[temp]=1;
r[j]=1;
}
temp=temp+1;
}
q[i]=1;
}
else
{
q[i]=0;
}
}
printf("the quotient is\n");
for(i=0;i<m;i++)
{
printf("%d",q[i]);
}
printf("the  remainder is\n");
for(i=0;i<n;i++)
{
printf("%d",r[i]);
}
}


................................................................

#include<stdio.h>
#define INFINITY 9999
void main()
{
  int a[20][20],c[20][20],i,j,m,n,d[10],min_d,nextnode,p[10],u,e,visit[10],count;
  printf("Enter m,n");
  scanf("%d %d",&m,&n);
  printf("Enter adjacency matrix");
  for(i=0;i<m;i++)
  {
    for(j=0;j<n;j++)
    {
      scanf("%d",&a[i][j]);
    }
  }
  printf("Adjacency matrix is");
  for(i=0;i<m;i++)
  {
    printf("\n");
    for(j=0;j<n;j++)
    {
      printf("  %d",a[i][j]);
    }
  }
  for(i=0;i<m;i++)
  {
    for(j=0;j<n;j++)
    {
      { if(i==j)
          c[i][j]=0;
        else if(a[i][j]==0)
          c[i][j]=INFINITY;
        else
          c[i][j]=a[i][j];
      }
    }
  }
  printf("\nThe cost matrix is:");
  for(i=0;i<m;i++)
  {
    printf("\n");
    for(j=0;j<n;j++)
    {
      printf("  %d",c[i][j]);
    }
  }
   printf("\nEnter the starting node:");
	scanf("%d",&u);
   printf("\nEnter the ending node:");
     scanf("%d",&e);
  	for(i=0;i<n;i++)
	{
		d[i]=c[u][i];
		p[i]=u;
		visit[i]=0;
	}
	
	d[u]=0;
	visit[u]=1;
	count=1;
	
	while(count<n-1)
	{
		min_d=INFINITY;
		for(i=0;i<n;i++)
			if(d[i]<min_d && !visit[i])
			{
				min_d=d[i];
				nextnode=i;
			}			
			visit[nextnode]=1;
			for(i=0;i<n;i++)
				if(!visit[i])
					if(min_d+c[nextnode][i]<d[i])
					{
						d[i]=min_d+c[nextnode][i];
						p[i]=nextnode;
					}
		count++;
	}
	for(i=0;i<n;i++)
		if(i!=u)
		{
		  if(i==e)
		  {
			printf("\nDistance of node%d=%d",i,d[i]);
			printf("\nPath=%d",i);
			
			j=i;
			do
			{
				
				j=p[j];
				printf("<-%d",j);
			}while(j!=u);
	      }
        }
}
....................................................................
