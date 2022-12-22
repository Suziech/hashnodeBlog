# [JavaScript] Selecting HTML Elements.

## 1. getElement*s*ByTagName*("TagName")*

when you use the mentioned one, you will get all the elements from the HTML as below.

<em>HTML</em>
```
    <ul id="list">
        <li class = "item">
            <a href = "http://www.google.com">Google</a>
        </li>  
        <li class = "item">Second</li>
        <li class = "item">Third</li>
    </ul>
``` 
<hr>

<em>Executing JavaScript</em>
```
document.getElementsByTagName("li");
->
HTMLCollection(3) [li.item, li.item, li.item]
0: li.item
1: li.item
2: li.item
length: 3
[[Prototype]]: HTMLCollection
``` 
<hr>

<em>Getting length of the Tag (the number of Tag)</em>
```
document.getElementsByTagName("li").length;
-> 3
``` 
<hr>

If you want to change the style of the tag, you should use "[]" to specify.

```
document.getElementsByTagName("li")[2].style.color = "purple";
'purple'
``` 
Result :

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657091897740/eCVkLQOgo.png align="left")

## 2. getElement*s*ByClassName*("ClassName")*
<em>HTML</em>
```
    <button class = "btn">Click me</button>
``` 
<hr>
<em>Executing JavaScript and change coluor of the element.</em>
Even though there is only one class in one HTML, "[]"must be used to point. otherwise, it won't work.
```
document.getElementsByClassName("btn");
-> HTMLCollection [button.btn]
document.getElementsByClassName("btn")[0].style.color = "green";
-> 'green'
``` 

Result :

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657092474057/7sxbQ-7or.png align="left")

## 3. getElementById*("Id")*

<em>HTML</em>
```
 <h1 id = "title">Hello</h1>
``` 
<hr>
<em>Executing JavaScript and change the font colour and the text.</em>
Because Id is unique itself, '[]' is not needed to change its property.

```
document.getElementById("title");
<em>HTML</em>
-> <h1 id=​"title">​Hello​</h1>​
document.getElementById("title").style.color = "brown";
-> 'brown'
document.getElementById("title").innerHTML = "Good Bye";
-> 'Good Bye'
``` 

Result : 
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657092957526/sJRLnGIV0.png align="left")

## 4. querySelector*("Selector")*⭐️

I think this one is the best for usage as it can be very specified and used for element, class, id selectors.

<em>HTML</em>
```
<body>
    
    <h1 id = "title">Hello</h1>
    <a href = "http://www.google.com">Google</a>
    <input type = "checkbox">

    <button class = 
    "btn">Click me</button>

    <ul id="list">
        <li class = "item">
            <a href = "http://www.google.com">Google</a>
        </li>  
        <li class = "item">Second</li>
        <li class = "item">Third</li>
    </ul>
</body>
``` 
<hr>
<em>For this mentioned one, Selector can be used like we use for CSS.
Please see the example how to use HTML element by using selector.</em>

```
document.querySelector("h1").style.color = "blue";
-> 'blue'
document.querySelector(".btn").style.color = "red";
-> 'red'
document.querySelector("#list").style.color = "orange";
-> 'orange'
``` 

Result : 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657094642652/RUbmKWHI5.png align="left")

<hr>
<em>It is possible to use multiple selector to choose more specific one as below.</em>

```
document.querySelector("#list .item").style.color = "red";
'red'
``` 
Result : 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657095369248/zqogbp7xo.png align="left")

<hr>

<em>However, above one will just select first one even though there are several classes under the same name. in this case, we can use <strong>querySelectorAll("Selector")</strong></em>

```
document.querySelectorAll("#list .item")
-> NodeList(3) [li.item, li.item, li.item]
0: li.item
1: li.item
2: li.item
length: 3
[[Prototype]]: NodeList
``` 

## My concern 🤔
> I've got a question about <strong>querySelectorAll("Selector")</strong>. It is possible to select multiple elements but there's error if I want to change the style of the multiple element to the same colour. if I code **document.querySelectorAll("#list .item")[0,1,2], there's no error but only [2] will be changed to red. If you know the answer why, please comment for me. Thank you!

-> I have found the answer! 🥹 please refer to https://suzie.hashnode.dev/questions#heading-how-to-make-several-elements-to-change-the-properties

*Source - Udemy / Angela / 143. Selecting HTML Elements with Javascript*
