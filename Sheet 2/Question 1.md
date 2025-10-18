//Solved by Hoda Hatem

#include <iostream>
using namespace std;
class Toy{
    private:
        string name;
        float price, tax, net_price;  
    public:
        void read(){
            cin>>name>>price>>tax;
            net_price = price + (tax/100) * price;
        }
        float getnetprice(){
            return net_price;
        }
        void display(){
            cout<<"name: "<<name<<endl;
            cout<<"price: "<<price<<endl;
            cout<<"tax: "<<tax<<endl;
            cout<<"net_price: "<<net_price<<endl;
        }
        Toy compare(Toy t1){
            if(net_price>t1.net_price){
                return *this;
            }
            return t1;
        }
};
int main(){
    int n;
    cin>>n;
    Toy toys[n];
    cout<<"enter data for toys: "<<endl;
    for (int i = 0; i < n; i++)
    {
        cout<<"Enter data for toy:["<<i<<"]: "<<endl;
        toys[i].read();
    }

    cout<<"toys have net_price grater than 50: "<<endl;
    for (int i = 0; i < n; i++){
        if(toys[i].getnetprice()>50){
            toys[i].display();
        }
    }

    Toy maxToy = toys[0].compare(toys[n - 1]);
    cout << "Toy with maximum net price between first and last:"<<endl;
    maxToy.display();
 
    return 0;
}
