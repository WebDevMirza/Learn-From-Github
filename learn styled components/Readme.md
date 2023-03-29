###### Learn styled components

<div align="center">
    <img src="./assets/styled-components.png" alt="styled components" width="150" height="auto"/>
    <h1>Welcome to Learn NPM</h1>
</div>

<details open>
    <summary><h2>Table of Contains</h2></summary>
    <ol>
        <li>
            <a href="#about-styled-components">About Styled Components</a>
        </li>
        <li>
            <a href="#getting-started">Getting Started</a>
            <ul>
                <li><a href="#installation">Installation</a></li>
                <li><a href="#basic-folder-structure">Basic Folder Structure</a></li>
            </ul>
        </li>
        <li>
            <a href="#learning-path">Learning Path</a>
            <ul>
                <li><a href="#making-simple-styled-components">Making Simple Styled Components</a></li>
            </ul>
        </li>
            <li><a href="#conclusion">Conclusion</a></li>
            <li><a href="#author">Author</a></li>
            <li><a href="#contributions">Contributions</a></li>
        </li>
    </ol>

</details>

# About Styled Components

npm packages, publishing packages, and managing dependencies.

Overall,

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

## H2

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

# Getting Started

Al


```cmd
npm <command>
```
<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

## Installation

```markdown
npm install styled-components
```

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

## Basic Folder Structure

```markdown
project/
├──src/
|  ├──assets/
│  ├──components/
|  |  ├──header
|  |  |  ├──Header.styled.jsx
|  |  |  ├──Header.jsx
|  |  ├──hero
|  |  |  ├──Hero.styled.jsx
|  |  |  ├──Hero.jsx
|  |  ├──footer
|  |  |  ├──Footer.styled.jsx
|  |  |  ├──Footer.jsx
|  |  ├──utills
|  |  |  ├──Basic.styled.jsx
|  |  |  ├──Container.styled.jsx
|  |  |  ├──Global.styled.jsx
│  ├──app.jsx
│  ├──main.jsx
├──package.json
├──README.md
```

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

# Learning Path

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

## Making Simple Styled Components

Let's say, we want to make a title with `h1` tag and give some style in it like bellow:

![image](https://user-images.githubusercontent.com/116225566/228483947-e0cb7ef0-2991-455f-b547-0be4c18b216f.png)

### Step-by-step procedure: 
- `import styled`, 
- `select tag and write css`, 
- `export`, and 
- `use`.  😃 

**Step-1:** import `styled` form styled-components that have all `html` tags.
```jsx
// filename: Basic.styled.jsx
import styled from "styled-components";
```
**Step-2:** select `h1` tag from `styled` and inside two backticks (`` ` ``), put `css` code. That's it. Give it a variable name such as `Title`.
```jsx
// filename: Basic.styled.jsx
const Title = styled.h1`
  font-size: 2.5rem;
  color: #474547;
  letter-spacing: 0.05em;
  max-width: 20ch;
  text-align: center;
`;
```

**Step-3:** now export `Title`.
```jsx
// filename: Basic.styled.jsx
export { Title };
```


**Step-4:** use `Title` where you want to.
```jsx
// filename: Hero.jsx
import { Title } from "../utills/Basic.styled";

const Hero = () => {
  return (
    <>
      <Title>Welcome To Student Database System.</Title>
    </>
  );
};
```

### Make couple of more components:

![image](https://user-images.githubusercontent.com/116225566/228491395-b2525e58-25d8-43b5-a236-3b5b0ca3091b.png)

```jsx
import styled from "styled-components";

const Title = styled.h1`            // creates a `h1` tag 
  font-size: 2.5rem;
  color: #474547;
  letter-spacing: 0.05em;
  max-width: 20ch;
  text-align: center;
`;

const Subtitle = styled.h2`         // creates a `h2` tag 
  font-size: 1.125rem;
  color: #521e1e;
  letter-spacing: 0.04em;
  text-align: center;
  max-width: 30ch;
`;

const Text = styled.p`          // creates a `p` tag 
  font-size: 1rem;
  color: #2f323f;
  letter-spacing: 0.05em;
  line-height: 1.5;
`;

export { Title, Subtitle, Text };       // DON'T FORGET TO EXPORT

```

```jsx
import { Subtitle, Title, Text } from "../utills/Basic.styled";     // ALSO DON'T FORGET TO IMPORT THIS WHEN YOU USE IT!!!
```



<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

# Conclusion

At this point, .............

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

# Author

- Mirza Monirul Alam
- Full Stack Web Developer.

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

# Contributions

Any contributions will be appreciated. **THANK YOU**

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>
