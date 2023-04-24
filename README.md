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

//4.19日
//二分查找法
//例子：在有序数组中（例，1-10）中找到x（某值）
#include <stdio.h>
int main()
{
    int k = 0;
    int arr[] = { 1,2,3,4,5,6,7,8,9,10 };
    int left = 0;
    int right = sizeof(arr) / sizeof(arr[0]);      //注意sizeof
                  //该处是right表示数组中个数 =整体size/单个size
    printf("请输入您想查找的值：");
    scanf_s("%d", &k);
    //printf("%d", right); 不熟练，判断一下right是否正确
    while (left <= right)
    {
        int mid = (left + right) / 2;
        if (arr[mid] > k)
            right = mid - 1;
        else if (arr[mid] < k)
            left = mid + 1;
        else
        {
            printf("找到了，该值的下标为%d\n", mid);
            break;
        }
    }
    if (left > right)
        printf("未找到\n");
    return 0;
}

//4.20日 练习
// 例题1：编写代码，演示多个字符从两端移动，向中间汇聚。
//#include <stdio.h>
//#include <string.h>
//#include <Windows.h>
//#include <stdlib.h>
//
//int main()
//{
//    char arr1[] = "welcome to China!!!";
//    char arr2[] = "###################";
//    int left = 0;
//    /*int right = sizeof arr1 / sizeof arr1[0]- 2;*///由于是字符串，其最后一位自带一个
//     //此处的计算没有strlen简洁                                           // ‘/0’，所以需要再多减去一个
//    int right = strlen(arr1) - 1; //strlen计算字符串长度时，不计算‘/0’所以只减一。
//                //头文件为<string.h>
//    while (left<=right)
//    {
//        arr2[left] = arr1[left];
//        arr2[right] = arr1[right];
//        system("cls");        //该语句的命令是清空屏幕 ->其.h为<stdlib.h>
//        printf("%s\n", arr2);
//        Sleep(500); //为了更加鲜明，可以在此处休息一段时间 ，单位为ms
//                    //其头文件.h为<windows.h>
//        left++;
//        right--;
//     }
//
//    return 0;
//}
//2.编写代码实现，模拟用户登录场景，并且只能输入三次密码。
//若密码正确，则提示成功；若三次均错误，则退出程序。
//#include <stdio.h>
//#include <string.h>
//
//int main()
//{
//    int i;
//    char password[20] = {0};
//    for (i = 0; i < 3; i++)
//    {
//        printf("请输入密码（三次机会）:>");
//        scanf_s("%s",&password[20]);
//      //  if (password == "123456")    字符串之间不能用==来判断，应用strcmp；
//        if (strcmp(password, "123456") == 0) //strcmp即string compare 用来比较字符串
//            //若strcmp（A，B）中两者相等，则该整体输出为0；
//            //若A>B,则整体输出为正数；若A<B，则整体输出为负数。
//        {
//            printf("密码正确！\n");
//            break;
//        }
//        else
//            printf("密码错误！\n");
//    }
//    if (i == 3)
//        printf("三次密码均错误，退出程序。\n");
//    return 0;
//}

//3.例题：写代码将三个数按从大到小输出
//#include <stdio.h>
//int main()
//{
//    int a, b, c;
//    scanf_s("%d %d %d", &a, &b, &c);
//    if (a < b)
//    {
//        int tmp = a;    //搞出来个新变量去存储原来的值，免得赋值以后，以前的值没了
//        a = b;
//        b = tmp;
//    }
//    if(a<c)
//    {
//        int tmp = a;
//        a = c;
//        c = tmp;
//    }
//    if (b < c)
//    {
//        int tmp = b;
//        b = c;
//        c = tmp;
//    }
//    printf("%d %d %d", a, b, c); //那如果需要排列更多的数字咋办？？
//    return 0;
//}
//4.打印1-100中3的倍数
//#include<stdio.h>
//int main()
//{
//    int i;
//    for (i = 1;i < 101; i++)
//    {
//        if (0 == i % 3)       // %取模得到的为余数
//            printf("%d  ", i);
//    }
//    return 0;
//}
//5.求最大公约数，利用（辗转相除法）。
//#include <stdio.h>
//int main()
//{
//    int m = 24;
//    int n = 18;
//    int r;
//    scanf_s("%d %d", &m, &n);
//    while ((r = m % n)!= 0) //此处括号内也可只写成m%n，即当m%n为0时，跳出循环
//    {
//     /*   r = m % n;*/   //直接把重复的步骤写入括号内，简洁
//        m = n;
//        n = r;
//    }
// /*   if(m%n==0)*/
//        printf("公约数为%d", n);
//    return 0;
//}
//6.打印1000-2000之间的闰年 (闰年：1.能被4整除并且不能被100整除的年份的是闰年
//                                2.能被400整除的是闰年
//#include <stdio.h>
//int main()
//{
//    int i,count = 0;
//
//    printf("1000-2000之间的闰年有："); 
//    for (i = 1000; i < 2001; i++)
//    {
//        if ((i % 4 == 0 && i % 100 != 0) || i % 400 == 0)//进化版本 整体再使用逻辑或
//        {
//            printf("%d年 ", i);
//            count++;
//        }
//       /* else if(i%400==0)
//            printf("%d年 ", i);*/
//    } 
//    printf("count=%d", count);
//    return 0;
//}
//7.打印出100-200间的素数（质数） 利用试除法 例如13 应试除2-12的数字看其余数
//#include <stdio.h>
//#include <math.h>
//int main()
//{                              //这种情况是可以改进的
//    int i = 0;
//    int count = 0;
//    /*for (i = 100; i <= 200; i++) */  //第二种优化，100-200中的偶数可以直接跳过 
//    for (i = 101; i <= 200; i+=2)
//    {
//
//        int j = 0;
///*        for (j = 2; j < i; j++) */   //第一种优化，j没有必要到i，循环到根号i即可
//        for (j = 2; j <= sqrt(i); j++)             //或者到i/2即可，    i/2=>根号i
//        {                              //sqrt() 为开平方的数学库函数，
//            if (i % j == 0)           //即头文件为<math.h>
//                break;
//        }
//       /* if (j == i)*/       // 若上述循环条件不一样了，此处也需要改变
//        if(j > sqrt(i))      //与上端的小于等于相反
//        {
//            count++;
//            printf("%d  ", i);
//        }
//    }
//    printf("\ncount=%d\n", count);
//    return 0;
//}         

//4.21日练习
//习题1：编程程序数一下1-100中的数字出现了多少个9
//#include <stdio.h>
//int main()
//{
//	int count = 0;               //该题目的思想：若个位数是9，则i除10的余数为9
//	int i = 0;                    //若十位处是9，则i/10的商是9
//	for (i = 1; i <= 100; i++) //我认为此处也可以从9开始循环。
//	{
//		if (i / 10 == 9)
//			count++;
//		if (i % 10 == 9)      //此处不能用else if，因为else if和if只会运行一个
//			count++;
//	}
//	printf("%d", count);
//	return 0;
//}
//习题2：分数求和，计算1/1-1/2+1/3-1/4+...+1/99-1/100的值，并打印结果
//思路：分子都是一样的，可以利用循环增加分母 最后求和
//#include <stdio.h>
//int main()
//{
//	int i = 0;
//	int front = 1;
//	double sum = 0.0;
//	for (i = 1; i <= 100; i++)
//	{
//		sum += front*1.0 / i;        //该步骤会随着循环依次求和1/1+1/2..
//		front = -1 * front;        //用一个新变量在前端按要求乘-1
//	}
//	printf("sum=%lf", sum);  
//	return 0;
//}                          //注意该题目是分数，属于浮点型，应注意类型
//习题3:求10个整数中最大值
//思路：利用数组列出10个数字，然后依次比大小，记录下大值
//#include <stdio.h>
//int main()
//{
//	int arr[] = { 1,2,3,20,5,6,7,600,9,10 };
//	int max = arr[0];  //不应随意赋值，可能会导致结果不同，应该利用待比较的数字赋值
//	int i = 0;
//	for (i = 1; i < 10; i++) //由于arr[0]已经被赋值，可从第二个数字开始比较
//	{
//		if (max < arr[i])    //此步骤为将较大值存储到max内
//			max = arr[i];
//	}
//	printf("最大值为%d", max);
//	return 0;
//}
//习题4：在屏幕上打印9*9乘法表
//思路：
//1*1=1
//2*1=2 2*2=4
//3*1=3 3*2=6 3*3=9            相当于i行j列  有几列是看i的数值
//..                          利用这个规律去循环
//9*1=9 ...
//#include <stdio.h>
//int main()
//{
//	int i = 0;
//	for (i = 1; i < 10; i++)
//	{
//		int j = 1;
//		for (j = 1; j <= i; j++)
//		{
//			printf("%d*%d=%-2d  ", i, j, i * j); //%-2d代表占两个字符的位置，左对齐
//		}                                      //%2d是右对齐
//		printf("\n");
//	}
//	return 0;
//}
//4.22日 
//写一个猜1-100之间数字的游戏，可以重复玩，当猜大了会提示猜大了，猜小同理。
#include <stdio.h>
#include <time.h>
#include <stdlib.h>
int game()
{
	//printf("猜数字游戏\n");
	//1.生成随机数
	/*srand((unsigned int)time(NULL));*/ //若srand命令起始值在该位置，就会随着时间走
	int input = 0;                        //各值离得很近，并不是随机
	int ret = rand()%101;      //在rand之前应该先使用srand,不然起始值都是一样的
	 //rand模101余数肯定是1-100；同理，rand%100+1也可   //随机值的大小是0-3万多
	//printf("ret=%d", ret);
	//2.猜数循环
	while (1)
	{
		printf("请猜数字:>");
		scanf_s("%d", &input);
		if (input > ret)
		printf("猜大了\n");
		else if(input<ret)
			printf("猜小了\n");
		else
		{
			printf("猜对了\n");
			break;
		}
	}
	return 0;
}
int main()
{
	int i = 0;
	srand((unsigned int)time(NULL));     //尽量srand只使用一次，放到main中即可
	while (1)
	{
		printf("############################\n");
		printf("#######1.paly  0.exit#######\n");
		printf("############################\n");
		printf("请输入：");
		scanf_s("%d", &i);
		if (i == 1)
			game();
		else if (i == 0)
		{
			printf("退出程序\n");
			break;
		}
		else
			printf("输入错误，请重新输入(1/0)\n");
     }

	return 0;
}

//4.23日学习
//1.goto语句 
//#include <stdio.h>
//int main()
//{
//	again:
//	printf("haha\n"); 
//	goto again;      //该情况goto会直接循环到again的地方并且一直循环。
//	return 0;       //但是感觉用处不如其他几种循环
//}
//在多种嵌套下，适用于goto语句
//#include <stdio.h>
//int main()
//{
//	for(1)
//		for(1)
//			for ()
//			{
//				if (error)
//					goto adjust;   //在该种情况下，若想即使跳出几个嵌套的循环，
//			}                    //最好用goto语句，如果用break，需要多次使用，
//                           //还需要注意条件，防止出错。goto更简洁
//adjust:
//	....
//	return 0;
//}
//#include <stdio.h>
//#include <stdlib.h>
//#include <string.h>
//#define _CRT_SECURE_NO_WARNINGS
//#pragma warning(disable:4996)
//int main()
//{
//	char arr[20] = { 0 };
//	system("shutdown /s /t 60");
//	again:
//	printf("请注意您的电脑将会在一分钟后关机，若输入我是猪，就会取消关机\n请输入:>");
//	scanf("%s", arr,20);
//	if (strcmp(arr, "我是猪") == 0)
//	{
//		system("shutdown /a");
//	}
//	else
//		goto again;
//	return 0;
//}
//#include <stdio.h>
//int main()
//{
//	int i = 0;
//	for ( i = 0; i < 3; i++)
//	{
//		if (i == 2)
//			break;  //break之后 不会进入调整部分。
//	}
//	printf("i=%d", i);
//	return 0;
//}
//#include <stdio.h>
//#include <string.h>
//int main()
//{
//	char arr[] = "hello world"; //把hello换成*
//
//	memset(arr,'*', 5);
//	printf("%s", arr);
//	return 0;
//}          //注意学习库函数如何在网站上查找使用，工作会需要。
//自定义函数
//1.寻找两个数中较大的值
//#include <stdio.h>
////定义函数
//int get_max(int x, int y)
//{
//	return (x > y ? x : y);
//	//if (x > y)
//	//	return x;
//	//else
//	//	return y;
//}
//int main()
//{
//	int a = 20;
//	int b = 20;
//	scanf("%d %d", &a, &b);
//	//使用函数get_max 自定义函数
//	int max=get_max(a, b);
//	printf("较大值为%d", max);
//	return 0;
//}
// 学习：指针变量
//#include <stdio.h>
//int main()
//{
//	int a = 0;          //创建一个新的int类型
//	int* place= &a;     //&a是对a寻址，然后用int* 去存储其地址。此时place叫指针变量
//	*place = 10;        //*为解引用符号。当*后跟随指针变量时，也就是寻着该地址去找到 
//	printf("a=%d", a);    //其对应的变量a，此时我寻址后赋了值，打印后会出现a=10
//	return 0;
//}
// 
//2.写一个函数交换两个函数的内容
//#include <stdio.h>
//void change1(int x, int y)  //是不能完成任务的 //void 表示该函数没有返回值。
//{                     //原因：当实参传给形参式，形参其实是实参的一份临时拷贝，
//	int tmp = x;       //会重新创建空间进行操作，对形参的修改不会影响实参。
//	x = y;
//	y = tmp;          //这种情况下，x y会独立申请新的空间去运行函数，与主函数中
//                     //中的ab无关，不会根据指令改变他们的值
//}    // change1是传值调用，形参和实参分别占有不同的内存块，对形参修改不影响实参
//
//void change2(int* x, int* y) //而2中实参传过去的是地址，自定义函数根据地址寻到a，b
//{                         //x，y是指针变量，分别存放着a,b的地址
//	int tmp = *x;
//	*x = *y;
//	*y = tmp;           //change2是传址调用
//}
//int main()
//{
//	int a, b;
//	scanf("%d %d", &a, &b);
//	printf("a=%d b=%d\n", a, b);
//	//change1(a, b);
//	change2(&a, &b);
//	printf("a=%d b=%d\n", a, b);
//	return 0;
//}
//3.练习:写一个函数判断一个数是否为素数
//1.100-200的素数
//#include <stdio.h>
//int is_prime(int x)
//{ 
//	int a = 0;
//	for (a = 2; a <= x / 2; a++)      //运用开平方函数sqrt（数）也可以 
//	{                                //记得引用头文件 ，<math.h>
//		if (x % a == 0)              
//			return 0;    //在此处直接return0，直接终止，这样从for循环出去的只有
//	}                   //不符合循环条件的数值，那么该数值也就是素数
//	return 1;      
//	//int a = 0;
//	//for (a = 2; a <= x/2; a++)
//	//{
//	//	if (x % a == 0)
//	//		break;              //该方法还可以优化
//	//	else
//	//		;
//	//}     
//	//if (a>x/2)
//	//{
//	//	return 1;
//	//}
//	//else
//	//	return 0;  
//}
//int main()
//{
//	int count = 0;
//	int i = 0;
//	for (i = 100; i <= 200; i++)
//	{
//		//判断i是否为素数
//		if (is_prime(i) == 1)
//		{
//			printf("%d ", i);
//			count++;
//		}
//	}
//	printf("\ncount=%d", count);
//	return 0;
//}

//4.24学习
//自定义函数 练习题1：写一个函数判断一年是不是闰年。
//例如1000-2000年： 能被4整除又不能被100整除的是闰年或者能被400整除的是闰年
//#include <stdio.h>
//int judge(int n)
//{
//	if (((n % 4 == 0) && (n % 100 != 0)) || (n % 400 == 0))
//		return 1;
//	else                   //打印应放在主函数中，这样能保证自定义函数的简洁单一
//		return 0;          //在别人使用时，也会方便，避免多余不需要的功能。
//}                     // 可复制性！
//int main()
//{
//	int year = 0;
//	int count = 0;
//	for (year = 1000; year <= 2000; year++)
//	{
//		int i =judge(year);
//		if (i == 1)
//		{
//			printf("%d ", year);
//			count++;
//		}
//	}	
//	printf("\ncount=%d", count);
//	return 0;
//}
//练习题2：写一个函数，实现有序数组的二分查找。
//例如有序数组为1-10
//#include <stdio.h>
//#include <string.h>    //       实际上此处y是指针，因为主函数中传递过来的值是地址
//int search            (int x,int y[],int sz) //形参和实参的名字是一样的也没关系，不影响
//{
//	int left, right;
//	//int sz = sizeof(y) / sizeof(y[0]); 此处不能使用
//	for (left=0,right=sz-1; left <= right;)
//	{
//		int mid = (left + right) / 2;
//		if (y[mid] > x)        //自己的理解：由于数组中各数字的地址是连续的，
//			right=mid-1;      //所以传过来一个地址就可以根据下标再搜寻其他位置的。
//		else if (y[mid] < x)
//	     	left=mid+1;
//		else
//		{
//			return mid;
//		}
//	}
//	////if (left > right) 多余，因为只有不满足循环的时候才会跳出，如果找到了直接结束了
//		return -1;
//}
//int main()
//{
//	int i=6;
//	int arr[] = {1,2,3,4,5,6,7,8,9,10};
//	int sz = sizeof(arr) / sizeof(arr[0]); //由于自定义函数内部不能计算大小
//	//scanf("%d", &i);                      //那就自己在主函数内计算。
//	     // 注意，此处arr传递过去的只是数组中第一个数字的地址，
//	//如果所有的数字都传递过去的话，拷贝一份占用的内存可能会过于大。
//	int ret=search(i,arr,sz);//二分查找函数，如果找到了返回这个数值的下标，如果没找到就返回-1.
//	if (ret == -1)  
//		printf("找不到\n");
//	else
//		printf("找到了，下标是%d\n", ret);
//	return 0;
//}
//练习题3：写一个函数，每调用一次这个函数，就会将num的值增加1.
//想法：自定义函数，利用传址，改变实参的大小。
//#include <stdio.h>
//void Add(int* x)
//{
//	/**x++;*/ //注意，++的优先级较高，会给p++，如果想寻址然后给实参增加，应该加上括号
//	(*x)++;    //第一种方法
//	//*x = *x + 1;  //2.第二种方法
//}
//int main()
//{
//	int num = 0;
//	Add(&num);
//	printf("sum=%d\n", num);
//	Add(&num);
//	printf("sum=%d\n", num);
//	Add(&num);
//	printf("sum=%d\n", num);
//	return 0;
//}
// 学习知识：链式访问 也就是用其他函数的结果值作为结果使用
//#include <stdio.h>
//#include <string.h> //string.h是负责字符串的一系列库函数的头文件
//int main()
//{
//	//int i = strlen("abcd");
//	//printf("i=%d\n", i);
//	//同理：我可以直接用strlen（“abcd”）作为输出结果替代
//	printf("%d\n", strlen("abcd"));
//	return 0;
//}

//学习知识：函数声明，函数调用，函数定义
//例如：写一个求和的函数
//#include <stdio.h>  //引用库函数，运用尖括号<>
//#include "Add.h"    //引用其他头文件中的自定义函数时，应该用""双引号
////函数声明
///*int Add(int x, int y); *///其中x 和y可以不加 ，只需写明类型即可
//int main()
//{
//	int a = 10;
//	int b = 20;
//	//函数调用
//	int sum = Add(a, b);
//	printf("sum=%d\n", sum);
//	return 0;
//}
//函数定义
//int Add(int x, int y)
//{
//	int z = x + y;
//	return z;
//}

//但是事实上函数声明和定义是分别再独立创建一个头文件和源文件来装的
//目的是为了更方便工作时分工合作，避免了不能在同一个源文件中进行敲代码。
