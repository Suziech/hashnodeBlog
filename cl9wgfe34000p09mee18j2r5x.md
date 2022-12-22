# try Axios

# What is <mark>Axios</mark>?

- it is a _promised-based_ HTTP Client for `node.js` and the browser.

# Features
1. Automatic transforms for JSON data
2. Transform request and response data
3. Make http request from node.js

### Let's make a simple random quote generator to practice `axios` using React!

## 1. install react 
you can start from `npx create-react-app [project folder name]

## 2. Install Axios 👩‍🔧

```
$ npm install axios
```

## 3. import Axios

- import axios like below in `App.js`

```
import axios from 'axios';
```

## 4. Create a button

```
import axios from 'axios';

function App() {
  return (
    <div>
    <button>Get Quote</button>
    </div>
  );
}

export default App;

```

## 5. Get the random quote data using Axios by clicking the button
- Random Quotes API : `https://api.quotable.io/random`
- you can use onClick to call the data by clicking the button
- create a variable to connet data via onClick 

```
import axios from 'axios';

function App() {
  const getQuote = () => {
    axios.get('https://api.quotable.io/random')
    .then(res => {
      console.log(res)
    })
  }
  return (
    <div>
    <button onClick={getQuote}>Get Quote</button>
    </div>
  );
}

export default App;


```
- you can check if the data is in through `console` in dev tool like below.
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1667199233327/3ArICyivL.png align="left")
- to access to the quote itself, `res.data.content` would bring the data we want.

## 6. Access to the quote data

```
import axios from 'axios';

function App() {
  const getQuote = () => {
    axios.get('https://api.quotable.io/random')
    .then(res => {
      console.log(res.data.content)
    })
  }
  return (
    <div>
    <button onClick={getQuote}>Get Quote</button>
    </div>
  );
}

export default App;

```


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1667199722521/KZvLlf0lf.png align="left")

- We can access to the data and able to check from the `console`

## 7. add `catch` to catch the error if any

```
//import {useState} from 'react';
import axios from 'axios';

function App() {
  const getQuote = () => {
    axios.get('https://api.quotable.io/random')
    .then(res => {
      console.log(res.data.content)
    })
    .catch(err => {
      console.log(err)
    })
  }
  return (
    <div>
    <button onClick={getQuote}>Get Quote</button>
    </div>
  );
}

export default App;
```

## 8. Add useState to render the random quotes for each clicks (completed one)
```
import {useState} from 'react';
import axios from 'axios';

function App() {
  const [quote, setQuote] = useState('')
  const getQuote = () => {
    axios.get('https://api.quotable.io/random')
    .then(res => {
      console.log(res.data.content)
      setQuote(res.data.content)
    })
    .catch(err => {
      console.log(err)
    })
  }
  return (
    <div>
    <button onClick={getQuote}>Get Quote</button>
    {quote && <p>{quote}</p>}
    </div>
  );
}

export default App;

```

Finished! you can style if you want.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1667205285908/P0nywomI_.png align="left")
