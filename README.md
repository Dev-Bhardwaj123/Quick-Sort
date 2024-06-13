# Quick-Sort
Given a user input unsorted array sort it using QuickSort technique in O(nlogn) time complexity
//QuickSort
#include<iostream>
#include<bits/stdc++.h>
using namespace std;

int partitionAroundArray(int arr[],int low,int high){
	int i=low,pivot=high,j=low;
	while(i<high){
		if(arr[i]<=arr[pivot]){
			swap(arr[i],arr[j]);
			i++;
			j++;
		}
		else{
			i++;
		}
	}
	swap(arr[i],arr[j]);
	return j;
}

void quickSort(int arr[],int low,int high){
	if(low<high){
	int pivotIndex=partitionAroundArray(arr,low,high);
	quickSort(arr,low,pivotIndex-1);
	quickSort(arr,pivotIndex+1,high);
	}
}

int main(){
	int n;
	cin>>n;
	int arr[n];
	for(int i=0;i<n;i++){
		cin>>arr[i];
	}
	quickSort(arr,0,n-1);
	for(int i=0;i<n;i++){
		cout<<arr[i]<<" ";
	}
	return 0;
}
