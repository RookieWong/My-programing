# My-programing
My creation
#include<stdio.h>
bool test1(int b1, int a1,int b2, int a2);
bool test2(int b1, int a1,int b2, int a2);
void printfA(int a[][2]);
bool comparS(void);
int stor[8][2]; 
int i,j;
#define SIZE 8
int count = 0;
int main (void) 
{
int j1,j2,j3,j4,j5,j6,j7,j8;
	for(j1 = 0; j1 < SIZE; j1++)
	{
		stor[0][0] = 0;
		stor[0][1] = {j1};
		for(j2 = 0; j2 < SIZE; j2++ )
		{
			stor[1][0] = 1;
			stor[1][1] = {j2};
			for(j3 = 0; j3 < SIZE; j3++ )
			{
				stor[2][0] = 2;
				stor[2][1] = {j3};
				for(j4 = 0; j4 < SIZE; j4++ )
				{
					stor[3][0] = 3;
					stor[3][1] ={j4};
					for(j5 = 0; j5 < SIZE; j5++ )
					{
						stor[4][0] = 4;
						stor[4][1] = {j5};
						for(j6 = 0; j6 < SIZE; j6++ )
						{
							stor[5][0] = 5;
							stor[5][1] = {j6};
							for(j7 = 0; j7 < SIZE; j7++ )
							{
								stor[6][0] = 6;
								stor[6][1] = {j7};
								for(j8 = 0; j8 < SIZE; j8++ )
								{
									stor[7][0] = 7;
									stor[7][1] ={j8};
									if(comparS())
									{
										count++;
										printfA(stor);
									}

								}
							}
						}
					}
				}
			}
		}
	}
		 
	 printf("八皇后问题总共有%d种摆法\n\n", count);
	 printf("坐标（行数，列数）\n行数表示： 0 - 7 ，列表示： 0 - 7\n"); 
	 getchar(); 
	 return 0;
}

bool test1(int b1, int a1,int b2, int a2) {  //横纵坐标测试 
	bool bo = (a1 != a2);
	return bo;
} 

bool test2(int b1, int a1,int b2, int a2) {   //斜向坐标测试 
	bool bo = (b2 - b1 != a2 - a1) && (b1 - b2 != a2 - a1);
	return bo;
}

void printfA(int a[][2])       //遍历并打印数组 stor
{
	int k1 = 0,k2 = 0;
	for(k1 = 0; k1 < 8; k1++)
	{
		printf("(%d,%d)  ",stor[k1][k2],stor[k1][k2 +1]);
	}
	putchar('\n');
}

bool comparS(void)    //测试函数
{
	bool bl = true;
	int m2,n2;
	for(m2 = 1; m2 < SIZE; m2++)
	{
		for(n2 = 0; n2 < m2; n2++)
		{
			if(test1(stor[m2][0],stor[m2][1],stor[n2][0],stor[n2][1]) && test2(stor[m2][0],stor[m2][1],stor[n2][0],stor[n2][1]))
				;
			else
			{
				bl = false;
				break;
			}
		}
	}
	if(bl == false)
		return false;
	else
	{
		return true;
	}
}
