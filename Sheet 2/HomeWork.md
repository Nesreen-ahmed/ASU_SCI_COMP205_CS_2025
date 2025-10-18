//solved by ENG:Mariam Mohammed

#include <iostream>
#include <cmath>

using namespace std;
struct Data{
	float R,I;
};
class Complex{
private:
	Data C[20];
	float D[20];
    int n;
public:
	void ReadFunc(){
		cout<<"Enter The Number Of N ";
		cin>>n;
		cout << "Enter Real and Imaginary parts of complex numbers:\n";
		for(int i=0;i<n;i++){
			cin>>C[i].I;
			cin>>C[i].R;
			D[i] = sqrt(pow(C[i].R , 2 ) + pow(C[i].I , 2));
		}
	}

	void DisplayFunc(){
		cout<<"Index\tComplex Number\tD[i]: ";
		cout<<"-------------------------------------\n";
		for(int i=0;i<n;i++){
			cout<<i+1<<"\t"<<C[i].R <<"+"<<C[i].I<<"i"<<"\t\t"<<D[i]<<endl;
		}
	}

    //You can sort in another way
    //feel free to write your code
	void SortFunc(){
		for(int i=0 ;i <n-1 ; i++){
			for(int j= i+1 ; j<n ;j++){
				if(D[i]>D[j]){
				float TempD = D[i];
				D[i] = D[j];
				D[j] = TempD;

				Data TempC = C[i];
				C[i] = C[j];
				C[j] = TempC ;
			}
		}
		}
    }

	double AvgFunc(){
		double S= 0.0;
		for(int i= 0 ; i<n ; i++){
			S+=D[i];
		}
		return S/n;
	}

    //In Question:
    //a function to compare between the average of D for two objects and **display** the object with minimum value.
	void CompareAvgFunc(Complex H){
		if(AvgFunc () > H.AvgFunc())
            H.DisplayFunc();
        else DisplayFunc(); 
	}
};  

int main()
{
	Complex Obj1,Obj2;
	cout<<"Enter Info The First Object : \n";
	Obj1.ReadFunc();
	cout<<endl;
	cout<<"Enter Info The Second Object : \n";
	Obj2.ReadFunc();
	cout<<endl;
	cout<<"DisPlay The First Object Before Sort : \n";
	Obj1.DisplayFunc();
	cout<<endl;
	cout<<"DisPlay The Second Object Before Sort : \n";
	Obj2.DisplayFunc();
	cout<<endl;
	cout<<"After Sort The First Object Is : \n";
	Obj1.SortFunc();
	Obj1.DisplayFunc();
	cout<<"\t";
	cout<<"After Sort The Second Object Is : \n";
	Obj2.SortFunc();
	Obj2.DisplayFunc();
	cout<<endl;

	cout<<"The Avg Obj1 Is : "<<Obj1.AvgFunc();
	Obj1.AvgFunc();
	cout<<"\n";

	
	cout<<"The Avg Obj2 Is : "<<Obj2.AvgFunc();
	cout<<"\n";

    Obj1.CompareAvgFunc(Obj2);
	
    return 0;
}
