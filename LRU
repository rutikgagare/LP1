#include<bits/stdc++.h>
using namespace std;

int findOldest(map<int,int> m){
    int p = INT_MAX;
    int ans;
    
    for(auto i:m){
        if(i.second < p){
            p = i.second;
            ans = i.first;
        }
    }
    return ans;
}

void lru(int elements[], int n, int frameSize){
    vector<int> v;
    map<int,int> m;

    int hit = 0, miss = 0;

    for(int i=0; i<n; i++){
        if(v.size() < frameSize){
            if(find(v.begin(),v.end(),elements[i]) == v.end()){
                v.push_back(elements[i]);
                miss++;
            }
            else{
                hit++;
            }
            m[elements[i]] = i;
        }
        else{
            if(find(v.begin(),v.end(),elements[i]) == v.end()){
                int old = findOldest(m);
                m.erase(old);

                for(int j = 0; j<v.size(); j++){
                    if(v[j] == old){
                        v[j] = elements[i];
                        break;
                    }
                }
                miss++;
            }
            else{
                hit++;
            }
            m[elements[i]] = i;
        }

        cout<<"hits : "<<hit<<" miss : "<<miss<<endl;
        for(auto i:v){
            cout<<i<<" ";
        }
        cout<<endl;
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

    lru(elements,n,frameSize);
    return 0;
}
