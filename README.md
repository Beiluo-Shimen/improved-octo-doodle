# improved-octo-doodle
数据共享，开放学习
#include <stdio.h>
int main()
{
    int a[3][4];
    int i,j,k;
    int max,min,row,column;
    printf("请依次输入12个数字：\n");
    for(i=0;i<3;i++)
    {
        for(j=0;j<4;j++)
        {
            scanf("%d",&a[i][j]);
        }
    }
    
    for(i=0;i<3;i++)
    {
        //计算出第一行的最大值及对应列标
        max=a[i][0];
        column=0;
        for(j=0;j<3;j++)
        {
            if(max<a[i][j+1])
            {
                max=a[i][j+1];
                column=j+1;
            }
        }
        printf("\nmax=%d,column=%d\n",max,column);

        //依据上面的列标计算出该列的最小值
        min=a[0][column];
        row=0;
        for(k=0;k<2;k++)
        {
            if(min>a[k+1][column])
            {
                min=a[k+1][column];
                row=k++;
            }
        }
        printf("\nmin=%d,row=%d\n",min,row);

        //判断行的最大值与列的最小值是否相等
        if(max!=min)
        {
            if(i>=2) printf("\n数组无鞍点（数组的行中最大，列中最小）\n");
        }
        else
        {
            printf("\n%d是数组的鞍点（数组的行中最大，列中最小）\n",a[row][column]);
            break;
        }
    }

    return 0;
}
