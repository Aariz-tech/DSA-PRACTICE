# DSA-PRACTICE

ROTATE IMAGE PROBLEM 
----------------------------------------------------------------------
MY SOLUTION 
------------------------------------
#include <iostream>
using namespace std;

void rotateImage(int arr[][100], int m, int n) {
    for(int i = n-1;i>=0;i--) {
        for(int j=0;j<m;j++) {
            cout<<arr[j][i]<<" ";
        }
        cout<<endl;
    }
}

int main() {
    int m,n; 
    int arr[100][100];
    cin>>m>>n; 
    for(int i=0;i<m;i++) {
        for(int j=0;j<n;j++) {
            cin>>arr[i][j];
        }
    }
    
    rotateImage(arr,m,n);
	
	return 0;
}
------------------------------------------------------------
  PARTEEK BHAIYA SOLUTION 
 -------------------------------------------------
  #include <iostream>
#include <algorithm>
using namespace std;


void rotateArr(int arr[][100], int n) {
  //for reverse
    for(int i=0;i<n;i++) {
        int startCol = 0; 
        int endcol = n-1; 
        while(startCol < endcol) {
            swap(arr[i][startCol], arr[i][endcol]);
            startCol++; 
            endcol--;
        }
    }
  //for transpose
    for(int i=0;i<n;i++) {
        for(int j=0;j<n;j++) {
            if(i<j) {
                swap(arr[i][j], arr[j][i]);
            }
        }
    }
}
void rotate_STL(int arr[][100], int n) {
    for(int i = 0;i<n;i++) {
       reverse(arr[i], arr[i]+n);
    }
    for(int i=0;i<n;i++) {
        for(int j=0;j<n;j++) {
            if(i<j) {
                swap(arr[i][j], arr[j][i]);
            }
        }
    }
}

int main() {
    int m,n; 
    int arr[100][100];
    cin>>n; 
    for(int i=0;i<n;i++) {
        for(int j=0;j<n;j++) {
            cin>>arr[i][j];
        }
    }
    
    rotate_STL(arr,n);
    for(int i=0;i<n;i++) {
        for(int j=0;j<n;j++) {
            cout<<arr[i][j]<<" ";
        }
        cout<<endl;
    }
	
	return 0;
}

  
  -------------------------------------------
