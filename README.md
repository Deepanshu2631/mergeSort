# mergeSort
# code of merge sort using c++
#include <bits/stdc++.h>
using namespace std;
	void merge(int arr[] , int l , int mid  , int r){
		int n1 = mid-l+1;
		int n2 = r - mid;
		int a[n1];
		int b[n2];
		for (int i = 0; i < n1; ++i)
		{
			a[i] = arr[l+i];
		}
		for (int i = 0; i < n2; ++i)
		{
			b[i]=arr[mid+1+i];
		}
		int i =0;
		int j =0;
		int k = l;
		while(i<n1 && j<n2){
			if(a[i]<b[j]){
				arr[k]= a[i];
				i++;
				k++;
			}else{
				arr[k]=b[j];
				j++;
				k++;
			}
		}
		while(i<n1){
			arr[k]= a[i];
				i++;
				k++;
		}
		while(j<n2){
			arr[k]=b[j];
				j++;
				k++;
		}
	}
 	void mergesort(int arr[]  , int l , int r){
 		
 		if(l<r){
 			int mid = (l+r)/2;

 			mergesort(arr , l ,  mid);
 			mergesort(arr , mid+1 , r);
 			merge( arr , l , mid  , r);
 		}
 	}
int main(){
	int n ;
	cin>>n;

	int ar[n];
	for (int i = 0; i < n; ++i)
	{
		cin>>ar[i];
	}
	mergesort(ar , 0 , n);
	for (int i = 0; i < n; ++i)
	{
		cout<<ar[i]<<" ";
	}
}
