#include<iostream>
using namespace std;

void findWaitingTime(int n, int bt[],int wt[], int at[]){
	int service_time = at[0];
    wt[0] = 0;
	for (int i = 1; i < n ; i++){
		service_time += bt[i-1];
		wt[i] = service_time - at[i];

		if(wt[i]<0){
    		wt[i]=0;
    	}
	}
}

void findTurnAroundTime(int n, int bt[],int wt[], int tat[]){
	for (int i = 0; i < n ; i++){
		tat[i] = bt[i] + wt[i];
    }
}

void findCompletionTime(int n, int ct[],int at[],int tat[]){
	for(int i = 0; i < n ; i++){
		ct[i] = tat[i] + at[i];
    }
}

void findavgTime(int n, int bt[], int at[]){
	int wt[n], tat[n], ct[n];

	findWaitingTime(n, bt, wt, at);
	findTurnAroundTime(n, bt, wt, tat);
	findCompletionTime(n, ct, at, tat);

	cout <<" Arrival Time "<<" Burst Time "<<" Waiting Time "<<" Turn-Around Time "<<" Completion Time  "<<endl;

	int total_wt = 0, total_tat = 0;
	for(int i = 0 ; i < n ; i++){
		total_wt += wt[i];
		total_tat += tat[i];

		cout<<"  "<<at[i]<<"\t\t"<<bt[i]<<"\t\t"<<wt[i]<<"\t\t"<<tat[i]<<"\t\t"<<ct[i]<<endl;
	}

	cout<<"Average waiting time = "<<(float)total_wt/(float)n <<endl;
	cout<<"Average turn around time = "<<(float)total_tat/(float)n<<endl;
}

int main(){
	int burst_time[] = {5, 9, 6};
	int arrival_time[] = {1,2,3};

	findavgTime(3,burst_time,arrival_time);

	return 0;
}
