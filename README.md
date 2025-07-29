# sorting
//BUBBLE SORT.

import java.util.*;

public class Main {
    static int[] BubbleSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
        return arr;
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[]arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }
   int[]sorted = BubbleSort(arr);
        System.out.print(Arrays.toString(sorted));
    }
}
//Time Complexity==O(N*2)


//OPTIMISED CODE.

import java.util.*;

public class Main {
    static void BubbleSort(int[] arr) {
        int n = arr.length;
        boolean flag = false;
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    flag = true;
                }
            }
        }
        if (!flag) {
            return;
        }


    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[]arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }
     BubbleSort(arr);
        System.out.println(Arrays.toString(arr));
    }
}
//STRING SORT 
import java.util.Scanner;
public class Recursion {
    static String bubblesort(String s){
        char[] arr=s.toCharArray();
        for(int j=0;j< arr.length;j++) {
            for (int i = j + 1; i < arr.length - 1; i++) {
               if (arr[i] > arr[j]) {
                   char temp=arr[j];
                   arr[j]=arr[i];
                   arr[i]=temp;
               }
                }
            }
        return String.valueOf(arr);

    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String s = sc.next();
        String result = bubblesort(s);
        System.out.println(result);

    }
}
//SLECTION SORT.

import java.util.*;

public class Main {
   static int[] slectionSort(int[] arr){
       for(int i=0;i<arr.length;i++){
           int maxInt=i;
           for(int j=i+1;j<arr.length;j++){
               if(arr[j]<arr[maxInt]){
                   maxInt=j;
               }
           }
           int temp=arr[maxInt];
           arr[maxInt]=arr[i];
           arr[i]=temp;

       }
       return arr;
   }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[]arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }
        int[] res = slectionSort(arr);
       System.out.println(Arrays.toString(res));
    }
}
//INSERTION SORT

import java.util.*;

public class Main {
   static void insertionSorted(int[] arr) {
       for (int i = 1; i < arr.length; i++) {
           int j = i;
           while (j > 0 && arr[j - 1] > arr[j]) {
               int temp = arr[j];
               arr[j] = arr[j - 1];
               arr[j - 1] = temp;
               j--;
           }
       }
   }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[]arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }
        insertionSorted(arr);
        for(int val: arr) {
            System.out.print(val+" ");
        }

    }
}
/* sort arr[0,3,4,0,3,0] --[3,4,3,0,0,0] 
con 1. all element order are not change. 
con 2. all zero is set at last index.
 */
 import java.util.*;
 
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[]arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }
        for(int i=0;i<n;i++) {
            for (int j = i + 1; j < n - i - 1; j++) {
                if (arr[j] == 0 && arr[j + 1] != 0) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
            for(int num : arr) {
                System.out.print(num + " ");
        }
    }
}



/*Q. USING SLECTION SORT
 sort string[mahi, kafi, rani, sonu, pinky] --[kafi, mahi, pinky, rani, sonu ]
hint 1. a<b<...
hint 2. comper character and id first char is same chack second char.
 */

 import java.util.*;
 
public class Main {
    static void sortString(String[] str) {
        for (int i = 0; i < str.length - 1; i++) {
            int max_idx = i;
            for (int j = i + 1; j < str.length; j++) {
                if (str[j].compareTo(str[max_idx]) < 0) {
                    max_idx = j;
                }
            }
            String temp = str[max_idx];
            str[max_idx] = str[i];
            str[i] = temp;
        }
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        String[] str = new String[n];
        for (int i = 0; i < n; i++) {
            str[i] = sc.next();
        }
        sortString(str);
        for (int i = 0; i < n; i++) {
            System.out.print(str[i]+" ");
        }

    }
}
//MARGSORT.

import java.util.*;
public class Main {
    static void printArray(int[] arr){
        for (int i : arr) {
            System.out.print(i + " ");
        }
        System.out.println();
    }
  static void margsort(int[]arr,int l,int r){
        if(l>=r)return;
      int mid=(l+r)/2;
      margsort(arr,l,mid);
      margsort(arr,mid+1,r);
      marged(arr,mid,l,r);
  }
  static void marged(int[]arr,int mid,int l,int r){
      int n1=mid-l+1;
      int n2=r-mid;
      int[] left=new int[n1];
      int[] right=new int[n2];
      int i,j,k;
      for(i=0;i<n1;i++)left[i]=arr[l+i];
      for(i=0;i<n2;i++)right[i]=arr[mid+1+i];
      i=0;
      j=0;
      k=l;
      while(i<n1&&j<n2) {
          if (left[i] <= right[j]) {
              arr[k++] = left[i++];
          } else {
              arr[k++] = right[j++];
          }
      }
          while(i<n1)
              arr[k++]=left[i++];
          while(j<n2)
              arr[k++]=right[j++];

  }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] arr = new int[n];
        for(int i=0;i<n;i++){
           arr[i] = sc.nextInt();
        }
        System.out.println("before sort");
        printArray(arr);
        margsort(arr,0,n-1);
        System.out.println("after sort");
        printArray(arr);
    }
}
//QUICK SORT


import java.util.*;

public class Recursion{
  static void printArray(int[] arr){
      for(int i=0;i<arr.length;i++){
          System.out.print(arr[i]+" ");
      }
      System.out.println();
  }
  static void swap(int[] arr,int i,int j){
    int temp=arr[i];
    arr[i]=arr[j];
    arr[j]=temp;
  }
  static void quickSort(int[] arr,int l,int r){
    if(l>=r) return;
    int pi=partition(arr,l,r);
    quickSort(arr,l,pi-1);
    quickSort(arr,pi+1,r);
  }
  static int partition(int[] arr,int l,int r){
      int pivot=arr[l];
      int count=0;
      for(int i=l+1;i<=r;i++) {
          if (arr[i] <= pivot) {
              count++;
          }
      }
          int pivotIndex=l+count;
     swap(arr,l,pivotIndex);
     int i=l,j=r;
     while(i<pivotIndex && j<pivotIndex){
         while(arr[i]<=pivot)i++;
         while(arr[j]>pivot)j--;
         if(i<pivotIndex && j<pivotIndex){
             swap(arr,i,j);
             i++;
             j--;
         }
     }
     return pivotIndex;
  }
    public static void main(String[] args) {
           Scanner sc = new Scanner(System.in);
         int n = sc.nextInt();
        int[] arr = new int[n];
        for(int i=0;i<n;i++){
            arr[i]=sc.nextInt();
        }
        quickSort(arr,0,n-1);
        printArray(arr);
    }
    }
//COUNT SORT.


import java.util.Scanner;
public class Test{
    static int findMax(int []arr){
        int max=Integer.MIN_VALUE;
        for (int j : arr) {
            if (max < j) {
                max = j;
            }
        }
        return max;
    }
   static void countSort(int[] arr){
      int max=findMax(arr);
      int[] ans=new int[max+1];
      for(int i=0;i<arr.length;i++){
          ans[arr[i]]++;
      }
      int k=0;
      for(int i=0;i<ans.length;i++){
          for(int j=0;j<ans[i];j++){
              arr[k++]=i;
          }
      }
   }
   static void printArray(int[] arr){
       for (int j : arr) {
           System.out.print(j + " ");
       }
       System.out.println();
   }


    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n=sc.nextInt();
        int[] nums = new int[n];
        for(int i=0;i<n;i++){
            nums[i]=sc.nextInt();
        }
        countSort(nums);
        printArray(nums);
    }
}
