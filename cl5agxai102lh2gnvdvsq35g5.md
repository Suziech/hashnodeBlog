# Questions

I've decided to make a post about the questions I get during studying so I can check it out in the future.

# JavaScript
### 🙋‍♀️ How to make several elements to change the properties using DOM querySelectorAll?

```
[HTML]
      <h1>test</h1>
       <ul>
            <li class = "item">1</li>
            <li class = "item">2</li>
            <li class = "item">3</li>
        </ul>

[JavaScript]
       document.querySelector("item").style.color = "red";
``` 
> above will just change the colour of first item which is "1"

### ✅ I have found the answer!

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657164255492/sobjSU5jB.png align="left")
> I should have used the `for loop` to make all red. in the order of `[0] -> [1] -> [2]`

### 🙋‍♀️ How to set onclick on `<a>`tag?

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657180822397/VaPtQYKQo.png align="left")
> I want to change the colour of text which has <a>Tag but it doesn't work😭

### ✅ I have found the answer!

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657235819162/uTti1sTeO.png align="left")

> I've changed the selector tag to `<a>` instead of `<p>` and it worked! but why? do I need to specify the tag the one which is very close to the content?
