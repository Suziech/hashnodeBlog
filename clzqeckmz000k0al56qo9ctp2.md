---
title: "How to Get the Value Typed in an Input Element"
datePublished: Mon Aug 12 2024 02:50:49 GMT+0000 (Coordinated Universal Time)
cuid: clzqeckmz000k0al56qo9ctp2
slug: how-to-get-the-value-typed-in-an-input-element
tags: javascript, typescript

---

```javascript
import { useState } from "react";

function ToDoList() {

  const [value, setValue] = useState("");
  const onChange = (e:React.FormEvent<HTMLInputElement>) => {
    const {currentTarget : {value}} = e;
    setValue(value)
  }

  return (
    <div>
      <form>
        <input onChange={onChange} value={value} placeholder="Write a to do" />
        <button>Add</button>
      </form>
    </div>
  );
}

export default ToDoList;
```

I used to get the value using `event.target.value`, but I found another way to get the value from the input element as described above.

In most cases, especially with input elements, using [`e.target`](http://e.target)`.value` will work just fine. However, using `e.currentTarget.value` can be a safer choice in certain situations where you want to ensure that you’re getting the value from the specific element the event handler is attached to.