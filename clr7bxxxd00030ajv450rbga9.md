---
title: "Cool features of Styled components 💅"
seoTitle: "Cool features of styled-components"
seoDescription: "sharing cool features of styled components to reduce code duplications to have better readability"
datePublished: Wed Jan 10 2024 05:18:11 GMT+0000 (Coordinated Universal Time)
cuid: clr7bxxxd00030ajv450rbga9
slug: cool-features-of-styled-components
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1704863775213/b01f519e-448b-4d48-ab9b-e2dba4ba4395.avif
tags: reactjs, styled-components, css-in-js

---

I've realised why experienced developers say learning never stops. When I first tried styled components, I knew they were cool, but it was a bit tricky for a beginner. The official docs didn't make it crystal clear. Now, after a year as a developer, I've discovered some neat features of styled components.

So, what is `styled-components`?

It is a library that allows you to write CSS in JS while building custom components in Reactjs. one of the standout advantages of using Styled Components is its ability to create hassel-free themes for your application. (Source : google search)

Most of the cool stuff is about making things less repetitive.

why reducing code duplication is crucial maintainability and readability for several reasons:

* Easier Updates and Changes
    
* Enhanced Readability
    
* Faster Debugging
    
* Scalability
    
* Codebase Consistency
    
* Ease of Onboarding
    
* Resource Efficiency  
      
      
    1\. Styles that are Mostly the Same: No Need to Repeat CSS
    

Imagine this :

```javascript
//BEFORE
import styled from 'styled-components'

const Container = styled.div`
display: flex;
`
const Square = styled.div`
width: 100px;
height: 100px;
background-color:${(props) => props.bgColor};

`
const Circle = styled.div`
width: 100px;
height: 100px;
background-color:${(props) => props.bgColor};
border-radius: 50px;
`

function App() {
  return (
    <Container>
      <Square bgColor="red" />
      <Circle bgColor="blue" />
    </Container>
  );
}

export default App;
```

![the image above code created](https://cdn.hashnode.com/res/hashnode/image/upload/v1704457594679/bf4d051d-77e0-40f4-9dbb-b62451b95254.png align="center")

The `Square` and `Circle` code is almost the smae, making it long.  
But don't worry! Styled components can help you make it shorter:

```javascript
//AFTER
const Circle = styled(Square)`
border-radius: 50px;
`
```

Using `stlyed(Sqaure)` copies all the styles from `Square` to `Circle`. Props still work! This is one of the great features of styled components 👍

1. Simplify Same Attributes in HTML Tags
    

1. ```javascript
    //BEFORE
    import styled from 'styled-components'
    
    const Container = styled.div`
    display: flex;
    flex-direction: column;
    `
    const Input = styled.input`
    width: 50px;
    background-color:pink;
    
    `
    
    function App() {
      return (
        <Container>
          <Input required />
          <Input required />
          <Input required />
          <Input required />
          <Input required />
          <Input required />
          <Input required />
        </Container>
      );
    }
    
    export default App;
    ```
    
    If you need the same code with the same attributes, it can be simpler:
    

```javascript
//AFTER
const Input = styled.input.attrs({ required: true })`
width: 50px;
background-color:pink;
`
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704458003896/127faee1-4b1e-4b7d-96e1-001984d22e78.png align="center")

Adding `.attrs({required:true})` makes all the `Input` tags have the required attribute.

1. Same Styles, Different Tags: Use Different HTML Tags Easily
    

1. ```javascript
    //BEFORE
    
    import styled, { keyframes } from 'styled-components'
    
    const Wrapper = styled.div`
    display: flex;
    `
    
    const Text = styled.span`
    color: orange;
    `
    const Link = styled.a`
    color: orange;
    `
    
    function App() {
      return (
        <Wrapper>
          <Text>Hello</Text>
          <Link>This is the link</Link>
        </Wrapper>
      );
    }
    
    export default App;
    ```
    
    You don't need another styled-component function for a different HTML tag. Using \`as="html tag name you would like to change" solves the problem!
    

```javascript
//AFTER

import styled, { keyframes } from 'styled-components'

const Wrapper = styled.div`
display: flex;
`

const Text = styled.span`
color: orange;
`

function App() {
  return (
    <Wrapper>
      <Text>Hello</Text>
      <Text as="a">This is the link</Text>
    </Wrapper>
  );
}

export default App;
```

Thank you for joining me on this exploration of the cool features of styled components.  
  
Happy Coding ⭐