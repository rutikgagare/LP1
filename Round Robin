// C++ program for implementation of RR scheduling
#include<iostream>
using namespace std;

void findWaitingTime(int n,int bt[], int wt[], int quantum){
	int rem_bt[n];
	for(int i = 0 ; i < n ; i++){
		rem_bt[i] = bt[i];
    }

	int t = 0;
	while(1){
		bool done = true;
		for(int i = 0 ; i < n; i++){
			if(rem_bt[i] > 0){
				done = false; 
				if(rem_bt[i] > quantum){
					t += quantum;
					rem_bt[i] -= quantum;
				}
				else{
					t = t + rem_bt[i];
					wt[i] = t - bt[i];
					rem_bt[i] = 0;
				}
			}
		}
		if (done == true)
		    break;
	}
}

void findTurnAroundTime(int n,int bt[], int wt[], int tat[]){
	for (int i = 0; i < n ; i++)
		tat[i] = bt[i] + wt[i];
}

void roundRobin(int n, int bt[],int quantum){
	int wt[n], tat[n], total_wt = 0, total_tat = 0;

	findWaitingTime( n, bt, wt, quantum);
	findTurnAroundTime(n, bt, wt, tat);

	cout<<" Process "<<" Burst_Time "<<" Waiting_Time "<<" TurnAroundTime "<<endl;
	for (int i=0; i<n; i++){
		total_wt = total_wt + wt[i];
		total_tat = total_tat + tat[i];
		cout <<"  "<< i+1 <<" \t    "<< bt[i] <<"\t\t "<< wt[i]<<"\t\t "<<tat[i] <<endl;
	}

	cout << "Average waiting time = "<< (float)total_wt / (float)n;
	cout << "\nAverage turn around time = "<< (float)total_tat / (float)n;
}

int main(){
	int burst_time[] = {10, 5, 8};
    int n = sizeof burst_time / sizeof burst_time[0];

	int quantum = 2;
	roundRobin(n, burst_time, quantum);
	return 0;
}
