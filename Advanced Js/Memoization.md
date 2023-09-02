where a value of a pure function is **kept in memory** and reused when the **same arg is provided**. This is most useful in a recursion. In that sense a value is not **recalculated** again when the same prop or argument is provided.
This therefore making the value returned **instantaneous**.

**Example**
```javascript
const multiplyBy10 = (num)=>num*10; // simple pure function

const memo = (func) => {
	const cache = {};
	return (...params)=>{
		if (params.toString() in cache){
			// already cached no need to compute method	
			return cache[params.toString()];
		};
		// else compute the method and cache its value
		const value = func(...params);
		cache[params.toString()] = value;
		return value; // return the value after.
	};
}

// usage
const memoized = memo(multiplyBy10);
memoized(1); // compute and return 10.
memoized(3); // compute and return 30.
memoized(1); // will just return the memoized value.
memoized(3); //will return the memoized value without computing.
```


Note the following.
1. This best works for recursion.
2. This trades memory for speed.
3. Should think thoroughly before using for api request since data might change.