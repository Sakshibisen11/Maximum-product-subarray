# Maximum-product-subarray
To get a subarray with maximum product
import java.util.*;
class Main{
public static int max_product(int arr[]){
int max_so_far=0;
int max_ending=1;
int min_ending=1;

for(int i=0;i<arr.length;i++){
int temp=max_ending;
max_ending=Math.max(arr[i],Math.max(arr[i]*max_ending,arr[i]*min_ending));
min_ending=Math.min(arr[i],Math.min(arr[i]*temp,arr[i]*min_ending));
max_so_far=Math.max(max_so_far,max_ending);
}
return max_so_far;

}
public static void main(String args[]){
System.out.println("Enter array length");
Scanner sc=new Scanner(System.in);
int n=sc.nextInt();
int arr[]=new int[n];
System.out.println("Enter array elements");
for(int i=0;i<n;i++){
arr[i]=sc.nextInt();
}
System.out.print(max_product(arr));
}

}
}
