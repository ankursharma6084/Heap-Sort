# Heap-Sort
Heap Sort ALgorithm

#include<bits/stdc++.h>
using namespace std;

/****************************Template Ends*******************************/
 
 
<!--  // Don't let the worst get the best of you  -->


 class Solution
{
<!--     // public: -->
<!--     //Heapify function to maintain heap property. -->
    void heapify(int arr[], int n, int i)  
    {
         int mxIdx = i ;
         int left = 2*i+1 ;
         int right = 2*i+2 ;

         if(left < n && arr[left] > arr[mxIdx])
         {
            mxIdx = left ;
         }

         if(right < n && arr[right] > arr[mxIdx])
         {
            mxIdx = right ;
         }
         
         if(i!= mxIdx)
         {
            swap(arr[i] , arr[mxIdx]) ;
            heapify(arr , n , mxIdx) ;
         }
         
    }

<!--     // public -->
    //Function to build a Heap from array.
    void buildHeap(int arr[], int n)  
    { 
         for(int i=n/2-1 ; i>=0 ; i--)
         {
            heapify(arr , n , i) ;
         }
    }

    
    public:
<!--     //Function to sort an array using Heap Sort. -->
    void heapSort(int arr[], int n)
    {
         buildHeap(arr , n) ;

         while(n > 0)
         {
            swap(arr[0] , arr[n-1]);
            n--;
            heapify(arr , n , 0) ;
         }
    }
};

<!--   Input  -->
int32_t main()  {
 ios_base::sync_with_stdio(false);
  cin.tie(NULL);

  int n; cin>>n;
  int arr[n] ;
  for(int i=0; i<n; i++)
   cin>>arr[i] ;

  Solution s; 
  s.heapSort(arr , n) ;

  for(int i=0; i<n; i++)
   cout<<arr[i]<<" ";
   cout<<endl;
 
return 0;
}
