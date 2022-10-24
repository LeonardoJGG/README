# WEEK12

<details>
  <summary>Monday</summary>

1. Work on your project
  
</details>



<details>
  <summary>Tuesday</summary>

1. Work on your project
  
</details>




<details>
  <summary>Wednesday</summary>

## Age Prediction API 👶-👴

### API Requeriments:

* Use Express.JS to build the API.

* The API should be capable to response to any name.

* The API should use route parameters to get the name:

```javascript
# Request example
# Here samsepiol is the name the API should try to
# predict the age.
http://localhost:3000/api/age/samsepiol
```

* The age should be a random number that satisfies the condition: age > 0 && age < 100

* The response should include the age in days.

* The response should look similar to this one:

```javascript
{
  "name": "samsepiol",
  "age": "62",
  "days": "19366"
}
```

* If no name is provided in the request, the API should return an error message
prompting you to use the correct parameters:

```javascript
{
  "error": "Missing parameter 'name' was expected."
}
```

### Solution

* Step #1

```javascript
npm init -y
```

* Step #2

```javascript
npm install express --save
```

* Step #3 (coding)

```javascript
const express = require('express');
	
const api = express();
const port = 3000;

function getAge(min, max) { 
	return Math.floor(Math.random() * (100 - 1) + 1);
};

function ageToDays(age) {
	return age * 365;
};

api.use(express.json());

api.get('/api/age/', function (req, res) {
	const name = req.query.name;
	const age = getAge();
	const days = ageToDays(age);
	const result = {
		name: `${name}`,
		age: `${age}`,
		days: `${days}`
	};

	if(name == undefined || name == ''){
		const error = {"error": "Missing parameter 'name' was expected."};
		res.send(error);
	} else {res.send(result);}
	
	
});

api.listen(port, () => {
	console.log(`API IS RUNNING ON PORT ${port}`);
});
```

**Check the output of our program at** *http://localhost:3000/api/age/?name=your_name*

</details>




<details>
  <summary>Thursday</summary>

1. Work on your project

</details
