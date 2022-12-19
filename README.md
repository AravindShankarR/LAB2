# LAB2
Insertion sort
#include <iostream>
using namespace std;
void sort(int a[],int neg){
    for (int i=0;i<neg;i++){
        for(int j=0;j<neg-i-1;j++){
            if(a[j]>a[j+1]){
                int t = a[j];
                a[j] = a[j+1];
                a[j+1]  = t;
            }
        }
    }
}
void backsort(int a[],int neg){
    for (int i=0;i<neg;i++){
        for(int j=0;j<neg-i-1;j++){
            if(a[j]<a[j+1]){
                int t = a[j];
                a[j] = a[j+1];
                a[j+1]  = t;
            }
        }
    }
}
int main()
{
    int n;
    cin>>n;
    int a[n];
    int pos =0,neg = 0;
    for(int i=0;i<n;i++){
        cin>>a[i];
        if(a[i]<0){
            neg++;
        }
        else{
            pos++;
        }
        
    }
    int j=0,k=0;
    int b[neg],c[pos];
    for(int i=0;i<n;i++){
        if(a[i]<0){
            b[j] = a[i];
            j++;
        }
        else{
            c[k] = a[i];
            k++;
        }
    }
    backsort(b,neg);
    sort(c,pos);
    j=0,k=0;
    for(int i=0;i<neg;i++){
        a[i] = b[j];
        j++;
    }
    for(int i =neg;i<n;i++){
        a[i] = c[k];
        k++;
    }
    for(int i=0;i<n;i++){
        cout<<a[i]<<endl;
    }
    return 0;
}
