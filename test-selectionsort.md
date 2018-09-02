## 算法课练习一：选择排序 

### 把一列数按从小到大排序



思路：在所有数中找出最小的，与第一个位置的数交换位置，再从剩下的数中找最小的，继续与当前没有比较的数中的第一个位置交换，以此类推。



```java
public class SelectionSort {

    //选择排序
    //找出数组的最小值，和没有比较过的第一个位置的值比较，找出最小值，交换位置
    public static void sort(int arr[]){

        int n=arr.length;

        for(int i=0;i<n;i++){
            int minsite=i;

            //找出当前情况下最小值的位置
            for(int j=i+1;j<n;j++){
                if(arr[j]<arr[minsite]){
                    minsite=j;
                }
            }

            //与第i个位置交换,调用我定义的swap方法
            SelectionSort.swap(arr,i,minsite);
        }
    }

    //交换位置的函数,其实就是交换数组内元素的位置！
    //而我一开始理解成交换两个数的值了，具体我记录在Swap类中了，诶真是蠢蠢的
    public static void swap(int[] arr, int i,int j){
        int c=arr[i];
        arr[i]=arr[j];
        arr[j]=c;
    }

    //主函数
    public static void main(String[] args){

        //对象不用实例化，因为是静态全局的而不是对象，这个要补一下知识

        int arr[]={8,5,2,7,6,3,1,9};
        SelectionSort.sort(arr);//调用选择排序函数
        System.out.println("从小到大排序结果为：");
        for(int i=0;i<arr.length;i++){
          System.out.print(arr[i]);
          System.out.print(',');
        }

    }
```

在写这个的时候遇到一个问题，就是 **两个变量交换值 **的问题。

我会在另一个仓库里面记录

嘿嘿