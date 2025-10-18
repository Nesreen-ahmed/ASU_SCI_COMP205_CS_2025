//Solved by Nada..🤍💫

#include <iostream>
using namespace std;

int gcd(int a,int b) {
    if (b==0)
        return a;
    return gcd(b,a%b);
}

class GCD {
    int x[30],y[30],g[30],n;
public:
    void read() {
        cout<<"Enter Array size\n";
        cin>>n;
        for (int i=0;i<n;i++) {
            cout<<"Enter x["<<i<<"]: ";
            cin>>x[i];
            cout<<"enter y["<<i<<"]: ";
            cin>>y[i];
            g[i] = gcd(x[i],y[i]);
        }
    }
    void display() {
        cout<<"x\ty\tgcd(x,y)\n";
        for (int i=0;i<n;i++) {
            cout<<x[i]<<"\t"<<y[i]<<"\t"<<g[i]<<endl;
        }
    }
    GCD minn(GCD t) {
        int s1=0, s2=0;
        for (int i=0;i<n;i++) {
            s1+=g[i];
        }
        
        //loop on array size for object t. not n.
        for (int i=0;i<t.n;i++) {
            s2+=t.g[i];
        }

        if (s1<s2) {
            return *this;
        }
        return t;
    }
};

int main() {

    GCD a, b;
    cout << "Enter first set:\n";
    a.read();

    cout << "Enter second set:\n";
    b.read();

    cout << "\nFirst group:\n";
    a.display();

    cout << "\nSecond group:\n";
    b.display();

    GCD obj = a.minn(b);
    cout << "\nGroup with smaller min GCD:\n";
    obj.display();

    return 0;
}
