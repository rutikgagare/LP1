#include<iostream>
#include<bits/stdc++.h>
using namespace std;

void printData(queue<int> q){
    while(!q.empty()){
        cout<<q.front()<<" ";
        q.pop();
    }
    cout<<endl;
}

void fifo(int elements[],int n, int frameSize){
    set<int> s;  // for dealing with duplicates
    queue<int> q; // for dealing with fifo rule

    int hit = 0;
    int miss = 0;

    for(int i=0; i<n; i++){
        if(s.size() < frameSize){
            if(find(s.begin(),s.end(),elements[i]) == s.end()){
                s.insert(elements[i]);
                q.push(elements[i]);
                miss++;
            }
            else{
                hit++;
            }
        }
        else{
            if(find(s.begin(),s.end(),elements[i]) == s.end()){
                int temp = q.front();
                q.pop();
                q.push(elements[i]);

                s.erase(temp);
                s.insert(elements[i]);
                miss++;
            }
            else{
                hit++;
            }
        }
        cout<<"hits : "<<hit<<" miss : "<<miss<<endl;
        printData(q);
    } 
}

int main(){
    int n,frameSize;
    cout<<"Enter number of elements : ";
    cin>>n;

    int elements[n];
    for(int i=0; i<n; i++){
        cout<<"enter element : ";
        cin>>elements[i];
    }
    
    cout<<"Enter frame size : ";
    cin>>frameSize;

    fifo(elements,n,frameSize);

    return 0;
}
