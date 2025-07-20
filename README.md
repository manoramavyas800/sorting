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
