# 快速排序 #

&ensp;&ensp;:santa:快速排序是C.R.Hoare于1962年提出的划分交换排序，采用了一种分治策略。

```py
def quickSort2(aList,L,R):
    '''功能：快速排序
       输入：元素为数字类型的可比较的列表
       输出：元素从小到大排列的列表
    '''
    '''这个函数是在B站上看了BV1at411T75o写的'''
    L1=L
    R1=R
    #i是坑位的下标
    i=random.randrange(L1,R1)
    #pivot是本次排序的中轴数，小于pivot的放左边，大于等于pivot的放右边
    pivot=aList[i]
    #p(aList,i,pivot,L,R) 这种是调试用函数
    while L!=R:
        if aList[L]>=pivot:
            aList[i]=aList[L]
            i=L
            #p(aList,i,pivot,L,R)
            while L!=R:
                if aList[R]<pivot:
                    aList[i]=aList[R]
                    i=R
                    #p(aList,i,pivot,L,R)
                    break
                R-=1
        else:
            L+=1
    aList[L]=pivot
    #p(aList,i,pivot,L,R)
    #print("===================")
    if L1<i-2:
        #print("from",L1,"to",n)
        quickSort2(aList,L1,i-1)
    if i+2<R1:
        #print("from",m,"to",R1)
        quickSort2(aList,i+1,R1)


def p(aList,i,pivot,L,R):
    '''调试用函数
        输入：aList为一列表，i是当前坑位下标，pivot是中轴值，L左指针当前位置，R右指针当前位置
        输出：打印aList内容
    '''
    dic={i:"i",L:"L",R:"R"}
    for j in range(len(aList)):
        if j in dic:
            print(dic[j]+"=",end="")
        else:
            print("  ",end="")
        print(aList[j],end="")
        print(",",end="")
    print("pivot=",pivot,end="")
    print()

aList=[9,4,5,7,18,2,5,4,6,5,7,]
quickSort2(aList,0,len(aList)-1)
print(aList)
```
