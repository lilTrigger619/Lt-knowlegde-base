# About
The concept of curry function is used instead of taking multiple arguments in a function, only one argument is taken and a function is return which will take the next argument. This will continue until all the arguments are collected.
**Example**
```typescript
function iinp(firstname: string): (arg0: string) => unknown{
	// get first name first
	console.log(firstname);
	return function (last_name: string): (arg0: number) => unknown{
		// another function to get lastname
		const full_name = firstname + " " + last_name;
		console.log(full_name);
		return function (age: number): string {
			// get age and return the About user
			const about =
				"Full name is " + full_name + "\nYou are " + age + " years old.";
			console.log(about);
			return about;
		};
	};
}

let user:any = iinp("shadrack");
user = user("Opoku");
user = user(25);

```

From the above code, one can notice that instead of calling just one function with parameters, we used a curry  function to pass parameters down unto different functions.

