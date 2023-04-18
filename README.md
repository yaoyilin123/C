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


//4.16日学习和练习
//循环语句
////打印1-10的数字
//#include <stdio.h>
//int main()
//{
//	int i = 1;
//	while (i <= 10)     //括号里为真（非0      ）时，即进入while循环，执行里面的语句
//	{
//		printf("%d\n", i);    //当语句大于等于两句时，就应该加上{} 
//		                      //不然在该while循环下只会执行第一句
//		i++;
//	}
//	return 0;
//
//}


//判断continue和break的区别 
////1.break
//#include <stdio.h>
//int main()
//{
//	int a = 0;
//	while (a <= 6)
//	{
//		a++;
//		if (3 == a)      //!!!!!!注意 若是a=3 就是赋值 应该双等号
//			            //养成良好习惯，可以把数字放在前面
//			break;             
//		printf("a=%d\n", a);
//		
//	}                   //注意：该种形式，输出结果为1，2
//	                    //原因是while中的break会永久终止循环，
//	return 0;           //即break以后不会再进入while循环
//} 

//2.continue
#include <stdio.h>
int main()
{
	int i = 0;
	while (6 >= i)
	{
		i++;
		if (4==i)
			continue;            //continue 用于中止本次循环
		                         //在while循环中，若if中的语句为真，则continue启动
		                        //会终止当前循环，然后再次进入while循环，
		                         //该点与break不同！
		printf("i=%d\n", i); 
	}

	return 0;
}









//
//
//#include <stdio.h>
//int main()
//{
//	int ch;
//	ch = getchar();              //getchar 用来接收输入 
//	putchar(ch);                 //putchar 用来输出 ，比printf简洁
//	printf("\nch = % c\n", ch);  
//	return 0;
//}

//#include <stdio.h>
//int main()
//{
//	int ch = getchar();
//	while (ch != EOF)     //EOF=end of file -> -1
//	{                     //若输入EOF仍然不会中止运行，并且会打印出EOF
//                        //原因是：输入EOF是三个字母，输出会依次判断然后进行打印
//                         //ctrl+z 
//		putchar(ch);
//		printf("%c", ch);    //这样写代码 输入的如果不是正确值 会一直进行循环
//	}                     
//	return 0;
//}
////改进：
//int main()
//{
//	int ch;
//	while ((ch = getchar())!= EOF)  //不要忘记ch=getchar（）外的（）
//	{                                //是判断该整体是否等于EOF
//		putchar(ch);
//	}
//	return 0;
//}

//4.17日
//学习了getchar函数的实际意义，能读取掉输入缓冲区的多余部分
#include <stdio.h>
int main()
{
	int ch = 0;
	int ret = 0;
	char assword[] = {0};
	printf("请输入密码:>");
	scanf_s("%c",&assword); //输入一系列东西以后，该输入只会读取数字部分
	printf("请确认（Y/N）:>"); //其余多余部分会存储到输入缓冲区内，以等待下次输入读取
	while((ch=getchar())!='\n')//归根最后输入的回车，也就是\n 
	                            //该步骤运用while循环函数去除掉输入缓冲区里多余项； *重要！*
		                        //避免了后续输入读取错误，使编程错误
	{
		;
	}
	ret = getchar();       //由于输入缓冲区内没有东西，此处系统会再次等待输入 
	if (ret == 'Y')
		printf("确认成功");
	else
		printf("确认失败");
	return 0;
}

//4.18
//此处介绍for循环
//利用for循环打印1-10的数字
//#include <stdio.h>
//int main()
//{
//	int i;
//	for (i=1; i <= 10; i++)   
//      // 初始化；判断条件是否进入循环；调整
//	 //注意  此处的初始化只是给予一个类型赋值，需要在开头把类型声明 ->int i
//	{
//		printf("%d ", i);
//	}
//	return 0;
//}
//break 和continue在for循环和while循环中的作用是一样的
// break会直接终止循环并跳出，不再进行循环判断
// continue会中止当前循环，并重新进入循环做判断
// 
//此处介绍一种情况下for和while的区别,例子打印1-10数字，除了5
//1.while情况
//#include <stdio.h>
//int main()
//{
//	int i = 1;            //1.初始化
//	while (i <= 10)       //2.做循环判断    
//	{
//		if (5 == i)       //3.执行循环内部
//			continue;
//		printf("%d ", i);
//		i++;              //4.调整部分
//	}                
//	return 0;
//}           //如此编程会造成一种情况：在if判断为真，进入if语句，continue会跳出，
            //造成i++调整部分不会执行，使得该程序进入死循环，会一直进行判断。
//2.for循环
//#include <stdio.h>
//int main()
//{
//    int i;               
//    for (i = 1; i < 11; i++)
//   //  1.初始化2.判断 4.调整
//    {
//        if (5 == i)                    //3.表达语句
//            continue;                 // if为真，continue结束当前循环后，
//        printf("%d ", i);            //会进入调整 即i++，这与上面的while循环不同
//    }
//    return 0;
//}                   //for循环 是在语句结束以后，在进行调整

//注意：其中for（；；）括号中，可以是空白，但是不熟练不建议使用
 //          ↑会死循环
 


//
//#include <stdio.h>
//int main()
//{
//    int a;
//    for (a = 0; a = 0; a++)
//        printf("1");
//    return 0;
//}



//do while循环语句 ,例打印1-5
//#include<stdio.h>
//int main()
//{
//    int i = 1;
//    do                          //do 后加表达语句，直接执行表达语句，最后进行循环判断
//                                //这就意味着do while 循环必定会执行一次     
//    {
//        printf("i=%d\n", i);     //表达语句
//        i++;
//    }
//    while (i<6);                //循环判断 ，记得while后端加分号；
//    return 0;                  //do while 运用的最少
//}
//


//练习题
//1.计算n的阶乘
//#include <stdio.h>
//int main()
//{
//    int a ;
//    int n = 0;
//    int ret=1;
//    printf("求n的阶乘，请输入n值：");
//    scanf_s("%d", &n);         //该情况不考虑溢出，指数值过大
//    for (a = 1; a <= n; a++)
//    {
//        ret *= a;     //等同于 ret = ret * a;
//    }
//    printf("输入值n的阶乘为%d ", ret);
//    return 0;
//}
//
//

//2.计算1！+2！+...+10！
//#include <stdio.h>
//int main()
//{
//    int a=0;
//    int sum = 0;
//    int ret = 1;
//    for (a = 1; a <= 10; a++)
//    {
//        ret *= a;
//        sum += ret;           //注意：该种情况的sum和ret值不会清空~不要担心
//    }
//    printf("1！+2！+...+10！=%d",sum);
//    return 0;
//}
