#include<bits/stdc++.h>
using namespace std;

void optimal(int elements[], int n, int frameSize){
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
        }
        else{
            if(find(v.begin(),v.end(),elements[i]) == v.end()){
                for(auto p:v){
                    m[p] = -1;
                }

                for(int j = i; j<n; j++){
                    if(m[elements[j]] == -1){
                        m[elements[j]] = j;
                    }
                }

                int ans = INT_MIN;
                int opti = INT_MIN;

                for(auto p:v){
                    if(m[p] == -1){
                        ans = p;
                        break;
                    }
                }

                if(ans == INT_MIN){
                    for(auto q:m){
                        if(q.second > opti){
                            opti = q.second;
                            ans = q.first;
                        }
                    }
                }
                
                for(int r=0; r<v.size(); r++){
                    if(v[r] == ans){
                        v[r] = elements[i];
                    }
                }
                m.clear();
                miss++;
            }
            else{
                hit++;
            }
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

    // int elements[20] = {7,0,1,2,0,3,0,4,2,3,0,3,2,1,2,0,1,7,0,1};
    int elements[n];
    for(int i=0; i<n; i++){
        cout<<"enter element : ";
        cin>>elements[i];
    }
    
    cout<<"Enter frame size : ";
    cin>>frameSize;

    optimal(elements,n,frameSize);
    return 0;
}
