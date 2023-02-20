# Classess

In the new php 7 there is the introducction of classes. That is there is the introduction of object oriented programing. unlike javascript, php object notation is **->** instead of **.** .

	class A {
		function __construct($param){   // constructor
			$this->param = $param;
			echo("this will run when an instance or object is created");
			}
		private static $var_for_file_only = "something"; //only in this file
		protected static $var_for_class_only = "another"; //only in the class
		public static $var_access_anywhere = "again"; //accessible everywhere;
		
		private static function say(){
			echo "$this->param";
		}
		public function another(){
			echo "another $this->param";
		}
	}
	

**NOTE ::** the **__construct** has **two** underscores not one.

In the above code, there is the introdution of class for php. The **_construct** is a constructor for the class which will run 
all the necessary block beneth it.

###static
A static variable cannot be accessed from the instance of the of the class of from the object 
They are mainly for usage in the class unless realy necessary, to use outside which they will serve as **namespaces**

	echo A::$var_access_anywhere; //will work;
	
	$_a = new A(something);
	echo $_a->var_for_file_only // this or any other static varible will crush.

The above means whether **private, public or protected** the variable cannot be accessed from the class through an **object** or **instance**.

Also only **public static** can be used as a **namespace** in from a class;

This static idea is different from c++

### Public
meaning the object (variable or function) can be accessed both inside and outside the class

###Private
meaning the object(variable or function) can only be access in the class it was defined in and not in other **sub classess** or **inheritance** also cannot be accessed outside the class

###Protected
meaning the can be accessed in the class and other **sub classess** or **inheritance**;