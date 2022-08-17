# Namespaces
In a huge real world c++ program, using global keywords of c++ is very risky considerinig the fact that some c++ libraries have similar nameing keywords.

Therefore c++ introduces namespaces.
**namespaces** are a way to specify from which object's keyword or object you wanna use.

	namespace mynamespace {
	  static int number = 3;
	  int age;
	  void say(std::string);
	  void anotherSay(std:string){
	    std::cout << "another say but defined" << std::endl;
	    }
	}
	
	void mynamespace::anotherSay(std::string str){
	 std::cout << "This is a namespace function defined outside "
	 <<"the namespace" << std::endl;
	 }
	 
	 
The above code indicates that the use of namespace is very simple and can be used explicity.

##### Properties.
- They can be nested
- you can define other object from other namespaces in your namesapce as long as you call it from that namespace.

		namespace myNameSp {
		   static string cout (); //which is already defined in **std**
		   }
- Namespaces can be nested.

###using
The **using** keyword is used to declare the various names in a namesapce. It can also be used declare on only one function or varible in a namespace.

	namespace A {
	  int age = 2;
	  int age2;
	  using namespace std;
	  void say();
	  static void message(){
	  	using std::cout;
	  	cout << "this is from anoter namespace " << endl;
	  	}
	  }
	  
	  void message ();
	  
	  int main(){
	    using namespace std;
	    using A::say;
	    using A::message();
	    say();
	    message();
	    ::message():
	    
	    return 0;
	    }
	    
	   static void message(){
	   	using namespace std;
	   	cout << "hellow world"<<endl;
	   	}
	   	
In the above program, shows how namespaces are used.
T