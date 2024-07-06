#include <bits/stdc++.h> 
string gameWinner(vector<int> &arr, int n) {
	int count=1;
	int i=0;
	while(i<n-1){
		int j=i+1;
		while(j<n){
			long long int d=arr[i]-arr[j];
			if(d<0) d=(-d);
			int m=1;
			for(int k=0;k<n;k++){
				if(arr[k]==d){
					m=0;
					j++;
				
				}
				
			}
			if(m==1){
				count++;
				arr.push_back(d);
				n++;
				i=0;
				j++;
				
			}
		}
		i++;
	}
	if(count%2==0){
		return "Alice";
	}
	return "Bob";
	
}
