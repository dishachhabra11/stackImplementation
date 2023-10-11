#include <iostream>
using namespace std;
#include<stack>

class Stack{
  public:
  int *arr;
  int top;
  int size;
  Stack(int size){
    this->size=size;
    top=-1;
    arr=new int[size];
    
  }
  
  void push(int x){
    if(size-1-top>0){
      top++;
      arr[top]=x;
    }
    else {
      std::cout<<"stack overflow";
    }
  }

  void pop(){
    if(top<size && top>-1){
      top--;
    }
    else{
      cout<<"stack is empty";
    }
  }

  int peek(){
    return arr[top];
  }

  bool isEmpty(){
    if(top==-1)return true;
    else return false;
  }

};

int main(){
  Stack st(6);
  st.push(5);
  st.push(4);
  st.push(3);
  st.push(9);
  st.push(1);

  st.pop();
  st.pop();
  st.isEmpty();
  cout<<st.peek();
  cout<<st.isEmpty();
  st.pop();
  st.pop();
  cout<<st.peek();

}
