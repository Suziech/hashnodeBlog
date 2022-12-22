# [React] Dynamic Routing

# Why do we need "dynamic routing" ?

The basic way of setting the routing is static(pre-defined) way. In other words, Router components define all the paths that can be used and the components that you want to show when you access them in the project in advance. However, for complex and large applications, it can be difficult to handle just by presetting paths.

Let's say you develop your own blog. The essential elements of a blog are: 

1. List page where you can see the list of posts 
2. Detail page where you can see the contents of the post. 

Typically, if you set the list page to `/route`, set the detail page to `/post/[post ID]`, and enter `/post/1`, you will develop post 1 and post 2 when you connect to `/post/2`, and the Router component will look similar to the following.
```jsx
// Example of Router Components in a Blog Application - Static Routing

import React from 'react';
import { BrowserRouter, Route, Routes } from 'react-router-dom';

const Router = () => {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<ListComponent />} />
        <Route path="/post/1" element={<FirstPosting />} />
        <Route path="/post/2" element={<SecondPosting />} />
      </Routes>
    </BrowserRouter>
  );
};

export default Router;
```

When there are one or two blog posts, the above form will not be too much. However, as the number of blog posts is increasing, if 1000 posts are stacked, all routes from post/1 to 1000 should be set in the Router component. Also, if you delete a post in the middle, you must delete the route from the Router component again. Static routing, which defines all routers in advance, has the disadvantage of not being able to flexibly define routes.

The concept that came up to address these issues is dynamic routing. Dynamic routing solves the above problem by defining a specific rule and then setting it to show the element for a URL that matches the rule, rather than pre-defining the entire form of the URL when setting up a route. In the existing blog example, instead of pre-defining the entire form of the URL, including numbers such as 1 and 2, such as `/post/1`, `/post/2`, all URLs starting with `/post/` are set to link to the detail page.

Dynamic routing allows you to link to a detail page for any URL that meets the rule, such as `/post/1000`, `/post/1000`, `/post/100000`, and so on, making applications scalable. As a result, you do not need to modify the Router component directly, even if changes occur, such as adding or deleting posts.

# Implementation of Dynamic Routing with React-router-dom

Now that we know the concept of dynamic routing, let's see how to implement dynamic routing using the `react-router-dom` library for real projects. The example below assumes that `react-router-dom` is installed in the project.

A way to implement dynamic routing in react-router-dom is to utilise the `:` symbol in the path prop of the Route component. If you set the path in the form of a `path/:string`, whatever letter comes after the `path/ `in the URL, it will be connected to this route.

```jsx
// Example of Router Components in Blog Applications - Dynamic Routing

import React from 'react';
import { BrowserRouter, Route, Routes } from 'react-router-dom';

export default function Router() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<ListComponent />} />
        <Route path="/post/:id" element={<DetailPageComponent />} />
      </Routes>
    </BrowserRouter>
  );
}
```
If Route is set as shown in the example code above, no matter what letter comes after `/post/`, it will show the components of the detail page. This means that `/post/1000`, `/post/1000000`, `/post/test` are all linked to detail page components.

If you check the example link, you can see the detailed page if you connect to Route without setting a path such as `/post/1000`, `/post/1000`, `/post/1000000` on Route.

*where `:` the id followed by the symbol is the path parameter.*

# Dynamic Routing and Path Parameters

There is still one problem, although you do not need to statically set up all routes using dynamic routing. Now, even if the user enters the path set using dynamic routing, *only the same UI can be displayed*. If you look at an example of a blog application, you can only see the same detail page when a user enters any URL: `/post/1000`, `/post/1000000`. The final goal we want is to show the components of the detail page, but if the user accesses `/post/1`, the content of `post 1` is shown, and if the user accesses `/post/1000`, the content of `post 2` is shown. Path parameters can be useful at this time. The path parameter is to use the value in the URL as if it were a parameter. The path parameter allows you to process large frames to show the same but different UIs, just as different parameters can produce different results.

As mentioned above that you need to include a `path/: string` in the path prop of the route to set up dynamic routing. At this point, the name of the path parameter is written in the place of the string. Just as you can freely name the parameter in a function, you can also freely name the path parameter. In the example code, you set the path to `/post/:id`, so you set the path parameter to id. As a result, when the user accesses `post/1`, the value of 1 is passed under the name of id. If we write a code that performs a specific processing using the value transferred to the path parameter in the component, we will be able to show various UIs in the same component.

# Utilisation of Path Parameters

## useParams hook

react-router-dom provides `useParamshook`. UseParamshook makes it <mark>easy to get the value of the path parameter</mark> and provides a function to re-render components when the value of the path parameter changes like a state.

Calling `useParamshook` returns the value of *pathparams in **object** form*. At this time, the key of the object's property is the name of the path parameter set in Route, and the value is the value actually passed to the path parameter. In other words, the blog application named the path parameter as id, so if you accessed it with `post/1`, the return value of useParamshook would be {id:1}.

<table>
<tr><th>key</th><th> value</th></tr>
<tr><td>name of path parameter</td><td>value actually passed to the path parameter</td></tr>

</table>

```
// example of useParams

import { useParams } from 'react-router-dom';

const params = useParams();
// { [path-parameter-name]: value }
```
The path parameters value imported into useParams allows you to display various UIs in one component.

## Examples of Utilisation

### Assigning a Route to a Router Component with Dynamic Routing

You must first define a route for the list page and the detail page in Router. The detail page specifies the path through dynamic routing.

```
// src/Router.js

import { BrowserRouter, Routes, Route } from 'react-router-dom';
import List from './pages/List';
import Detail from './pages/Detail';

const App = () => {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<List />} />
        <Route path="/detail/:id" element={<Detail />} />
      </Routes>
    </BrowserRouter>
  );
};

export default App;
```


4-2-2. 리스트 컴포넌트에서 유저 리스트 표시
List 컴포넌트에서는 전체 유저 리스트를 보여줍니다. 이때 유저 리스트에 대한 정보는 /api/users API를 통해서 가져옵니다.


리스트에서 특정 유저를 클릭하면 해당 유저의 상세페이지로 이동하도록 Link 컴포넌트를 사용해 줍니다. Link 컴포넌트의 to prop에는 /detail/ Route로 이동시키되, /detail/ 뒤에 현재 클릭한 유저의 ID를 path parameter로 담아서 이동시킵니다.


// src/pages/List.js

import React, { useState, useEffect } from 'react';
import { Link } from 'react-router-dom';

const List = () => {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    fetch('https://reqres.in/api/users')
      .then((response) => response.json())
      .then((result) => setUsers(result.data));
  }, []);

  return (
    <section>
      <nav>
        {users.map(({ id, first_name, email, avatar }) => (
          <Link key={id} to={`/detail/${id}`}>
            <p>
              <strong>{first_name}</strong>
            </p>
            <p>{email}</p>
            <img alt="avatar" src={avatar} />
          </Link>
        ))}
      </nav>
    </section>
  );
};

export default List;



### Detail page components

The details page shows information about a single user. Information about the user is obtained through the `/api/users/[user's ID]` API. In order to use this API, you need to know the ID of the user that you need to show on the current detail page.

In this application, the path parameter included the user's ID in the path parameter when moving from the list page to the detail page, so in the detailed page, the value of the path parameter is obtained using the `useParamshook`, and then the UI is created through the result of calling the API.

```
// src/Detail.js

import React, { useState, useEffect } from 'react';
import { useParams } from 'react-router-dom';

const Detail = () => {
  const params = useParams(); // 1
  const userId = params.id; // 2

  const [user, setUser] = useState({});

  useEffect(() => {
    fetch(`https://reqres.in/api/users/${userId}`) // 3
      .then((response) => response.json())
      .then((result) => setUser(result.data));
  }, [userId]); // 4

  const { first_name, email, avatar } = user;

  return (
    <section>
      <article>
        <p>
          <strong>{first_name}</strong>
        </p>
        <p>{email}</p>
        <img alt="avatar" src={avatar} />
      </article>
    </section>
  );
};

export default Detail;
```

To interpreting the code above,

- UseParamshook to import parameters objects.
- Assign the value of the id property to the userId variable within the parameters object (access the id property because you set the name of the path parameter to /detail/:id when dynamic routing was set.)
- Proceed API call from inside useEffect.
- When determining the API URL to call, the API URL is dynamically determined using the userId value.
- Since the path parameter is set on the Router to show the information of the new user to the Detail component whenever the userId value changes, the userId is included in the dependency array of useEffect.
- By adding userId to the dependency array, whenever the value of userId changes, it is possible to make a new API call and change user state to show a new UI.
- If you want to check the actual behavior of the example code, you can check it through the example link.
