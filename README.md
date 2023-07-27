# C-p58---1-
C语言学习笔记 p58  自定义数据类型-枚举和共用体(1)
#include<stdio.h>
enum Sex
{
    //枚举的可能取值-常量
    MALE=2,
    FEMALE=4,
    SECRET=8//这里即使他是一个常量但我们也可以给他赋值，因为这是赋值初始值，和其他常量不一样
};

enum Color
{
    RED,
    GREEN,
    BLUE
};
int main()
{
    enum Sex s=MALE;
    enum Color c=BLUE;
    printf("%d%d%d\n",RED,GREEN,BLUE);//输出0，1，2。枚举里面的元素默认带有值，都从0开始
    return 0;
}


//联合-联合体-共用体
union Un
{
    char c;
    int i;
};
int main()
{
    union Un u;
    printf("%d\n",sizeof(u));
    printf("%p\n",&u);
    printf("%p\n",&(u.c));
    printf("%p\n",&(u.i));
    return 0;
}

check_sys()
{
    union Un
    {
        char c;
        int i;
    }u;
    u.i=1;
    return u.c;
}
int main()
{
    int a=1;
    int ret=check_sys();
    if(1==*(char*)&a)
    {
        printf("小端\n");
    }
    else
    {
        printf("大端\n");
    }
    //低地址--------->高地址
    //...[11][22][33][44]...   大端字节序存储模式
    //...[44][33][22][11]...   小端字节序存储模式
    //讨论一个数据，放在内存中存放字节的顺序
    
    return 0;
}


enum Sex
{
    MALE,
    FEMALE,
    SECRET
};

int main()
{
    enum Sex s=MALE;
    printf("%d\n",sizeof(s));
    return 0;
}//输出4
