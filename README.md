# C
存储C语言练习
//#include <stdio.h>
//
//int test()
//{
//	static int a = 1;      //static修饰的局部变量 使a成了一个静态的局部变量
//	a++;                    //使局部变量的生命周期变长了，即出了作用域也不会销毁
//	printf("a=%d\n", a);    
//}                          //static也可修饰全局变量，会使链接属性改变
//                              //也就是 不同文件的不能用了 即使用extern召唤也不行
//int main()                      //修饰函数和全局变量很类似 
//{ 
//	int i = 0;
//	while (i < 5)
//	{
//		test();
//		i++;
//	}
//	return 0;
//}

//
//#include <stdio.h>
//int main()
//{
//	int a = 0;
//	int* p = &a;    //此时p内存的是 a的地址     int*是 p的类型  &为取地址符号
//	printf("%d\n", p);  
//	*p = 10;        //* 解引用操作符 我的理解是用这个符号来寻着地址找到目标
//	printf("%d\n", a);
//	return 0;
//}



#define _CRT_SECURE_NO_WARNINGS
//#include <stdio.h>
//#include <string.h>  
//struct people          //结构体 - struct 
//{ 
//	char name[20];
//	int age;
//	char sex;
//};   //结构体}末尾要加分号；
//int main()
//{                                 //43行警告 int char转换什么玩意的
//	struct people A1 = {"Yaohaipeng",18,'man'};    
//	                 //为什么此处打印出来只能表示字符串末尾一个字母一个
//	printf("name=%s \nage=%d \nsex=%c\n ", A1.name, A1.age, A1.sex);
//	A1.age = 22;  //整形直接转换
//	strcpy(A1.name,"Yaoyilin");   //string copy字符串拷贝 
//	printf("name=%s \nage=%d\n", A1.name, A1.age);
//
//	struct people* pb = &A1;
//	printf("位置=%p", pb);
//			return 0;
//}

//
//
//#include <stdio.h>
//int main()
//{
//	int age = 18;
//	if (age < 18)
//		printf("未成年\n");
//	else if (age = 18)
//		printf("刚刚成年\n");
//	else
//		printf("成年\n");
//	return 0;
//}

//
//#include <stdio.h>
//int main()
//{
//	int age ;
//	scanf("%d", &age);
//	if (age < 18)
//	{
//		printf("未成年\n");
//	}
//	// else if(18<=age<28)  // 如果写成这个样子，前面的18<=age会先判断真假，
//	                        //那么就相当于0（假）或1（非0，真），那么__肯定<28
//	                        //程序就会识别错误。！
//	else if (18 <= age && age < 28)    //&& 逻辑与   
//	{
//		printf("青年\n");
//	}
//	else if (age >= 28 && age <= 50)
//	{
//		printf("壮年\n");
//	}
//	else
//	{
//		printf("老年\n");
//	}
//	return 0;
//}
//
//



//
//
//
//
//#include <stdio.h>
//int main()
//{
//	int a = 0;
//	int b = 2;
//	if (a == 1)
//		if (b == 2)
//			printf("hehe\n");
//
//		else                    //此处else和第二个if匹配
//			printf("haha\n");   //else和最近的未匹配的if进行匹配          
//	else
//		printf("ok");          //此处else和第一个if匹配！因为第二个已经匹配过了
//
//                   // 或者用{}进行区分    {}是一个代码块
//	return 0; 
//}                    
//
////运用分号区分例子：
//
//#include <stdio.h>
//int main()
//{
//	int a = 0;
//	int b = 2;
//	if (1 == a)
//	{
//		if (b = 2)
//			printf("hehe\n");
//	}
//	else
//	{
//		printf("haha\n");
//	}
//	return 0;
//}






//
////1.判断一个数是否为奇数
//#include <stdio.h>
//int main()
//{
//	int a = 0;
//	scanf("%d", &a);   //取地址&不要忘记！！
//	int b = a%2;       //%取模 用余数来判断是否为奇数
//	printf("b=%d\n", b);
//	if (0 != b)
//	{
//		printf("a是奇数\n");
//	}
//	else
//	{
//		printf("a是偶数\n");
//	}
//	return 0;
//}


//2.输出1-100之间的奇数
//#include <stdio.h>
//int main()
//{                       //与题意不符
//	int a=0;
//	scanf("%d", &a);
//	int b = a % 2;
//	if (0 != b)           //  !=表示不等于
//		printf("%d\n", a);
//
//	return 0;
////}
//
//int main()
//{
//	int a = 1;
//	while (a <= 100)
//	{
//		if (a % 2 != 0) //判断a是否为奇数 
//			printf("%d ", a);
//		a++;
//	}
//	return 0;
//}
//



////switch语句  用于多分支的情况 例如
////需要表示周几的时候
//#include <stdio.h>
//int main()
//{
//	int day = 0;
//	scanf("%d", &day);
//	if (1 == day)
//		printf("星期一");
//	if (2 == day)
//		printf("星期二");
//	if (3 == day)
//		printf("星期三");
//	if (4 == day)                 //这种情况过于繁琐 应该运用switch语句
//		printf("星期四");
//	//.....
//	return 0;
//}

//switch
//#include <stdio.h>
//int main()
//{
//	int day = 0;
//	scanf("%d", &day);
//	switch (day)  //(括号里必须是整形）
//	{
//	case 1:                 
//		printf("星期1");
//	case 2:
//		printf("星期2");
//	case 3:
//		printf("星期3");
//	case 4:
//		printf("星期4");
//	case 5:
//		printf("星期5");
//	case 6:
//		printf("星期6");
//	case 7:
//		printf("星期7");
//
//			//该情况未运用break    输入___ 会从case __进入，但是会一直向下运行
//		    //没有停止
//			
//	}
//	return 0;
////}
//
//#include <stdio.h>
//int main()
//{
//	int day = 0;
//	scanf("%d", &day);
//	switch (day)  //(括号里必须是整形）
//	{
//	case 1:
//		printf("星期1");
//		break;
//	case 2:
//		printf("星期2");
//		break;
//	case 3:
//		printf("星期1");
//		break;
//	case 4:
//		printf("星期1");
//		break;
//	case 5:
//		printf("星期2");
//		break;
//	case 6:
//		printf("星期1");
//		break;
//	case 7:
//		printf("星期2");
//		break;
//	//但是如果输入的不是我设定的值应该怎么办？？
//		//此时应该运用default
//	default:
//		printf("输入错误，请输入1-7");
//		break;  //养成良好习惯 default后也要加default  此外default在switch中位置
//		         //不受限制 放最开始也可
//
//	}
//	return 0;
//}
//
//
//#include <stdio.h>
//int main()
//{
//	int n = 1;
//	int m = 2;
//	switch (n)
//	{
//	case 1:m++;
//	case 2:n++;
//	case 3:
//		switch (n)       //switch可以嵌套！
//		{
//		case 1:n++;
//		case 2:m++; n++;
//			break;            //注：并不是switch所有的case语句都需要break
//		}                     //break 直接中止
//	case 4:m++;
//		break;
//	default:
//		break; 
//	}
//	printf("m=%d n=%d", m, n);
//	return 0;
////}
//
//#include <stdio.h>
//int main()
//{
//	int num = 0;
//	scanf("%d",&num);
//	if (num <= 10 || num >=50)          //  &| 逻辑或，仅有一个成立即可
//		printf("偏");
//	else
//		printf("中间");
//		
//	return 0;
//}


#include <stdio.h>
int main() 
{
	int day;
	scanf("%d", &day);
	switch (day)  //()里面必须是整形
	{
	case 1:
	case 2:
	case 3:
	case 4:
	case 5:
		printf("工作日");    //并不是每一个case入口都需要break
		break;
	case 6:
	case 7:
		printf("休息日");
		break;
	default:
		printf("输入错误，请输入数字1-7");
		break;
	}
	return 0;
}
