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
                    <li><a href="#sample-folder-structure">Sample Folder Structure</a></li>
                </ul>
            </li>
            <li>
                <a href="#learning-path-the-basic-part">Learning Path: The Basic Part</a>
                <ul>
                    <li><a href="#making-simple-styled-components">Making Simple Styled Components</a></li>
                    <li><a href="#styling-components-children">Styling Components Children</a></li>
                    <li><a href="#using-pseudo-classes-and-pseudo-elements">Using Pseudo-classes and Pseudo-elements</a></li>
                    <li><a href="#applying-global-styles">Applying Global Styles</a></li>
                    <li><a href="#adding-wrappers-or-containers">Adding Wrappers Or Containers</a></li>
                    <li><a href="#media-query-features">Media Query Features</a></li>
                </ul>
            </li>
            <li>
                <a href="#learning-path-the-intermediate-part">Learning Path: The Intermediate Part</a>
                <ul>
                    <li><a href="#extending-styles">Extending Styles</a></li>
                    <li><a href="#applying-variables">Applying Variables</a></li>
                    <li><a href="#applying-props">Applying Props</a></li>
                    <li><a href="#applying-as-polymorphic-prop">Applying as Polymorphic Prop</a></li>
                    <li><a href="#applying-attrs">Applying attrs</a></li>
                </ul>
            </li>
            <li>
                <a href="#learning-path-the-advanced-part-theming">Learning Path: The Advanced Part (Theming)</a>
                <ul>
                    <li><a href="#extending-styles">h2 - Theming</a></li>
                </ul>
            </li>
            <li><a href="#conclusion">Conclusion</a></li>
            <li><a href="#author">Author</a></li>
            <li><a href="#contributions">Contributions</a></li>
        </li>
    </ol>

</details>

# About Styled Components

Styled Components is a popular library for React applications that allows us to write CSS code in JavaScript files, which can help us better manage the styling of components. With Styled Components, we can define styled components using `tagged template literals`, which provide a way to write CSS code as a string within a JavaScript template literal. 

It provides reusable and maintainable CSS code, in addition to using props. Other css features such as media queries, pseudo-classes, and animations are also available in styled Components. All these features along with global styles, theming, and server-side rendering make Styled Components a powerful tool for building complex and dynamic web applications.


<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>


# Getting Started

All you need is to install `styled-components` through npm or yarn, and now you are ready to go with `react`.

## Installation

```markdown
npm install styled-components
```

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

## Sample Folder Structure

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

# Learning Path: The Basic Part

In this basic part, it will cover how to add html tag through styled components, how to use children's components along with their pseudo classes and pseudo elements, how to apply global styling, and how to deal with wrapper or containers in css.


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
// filename: Basic.styled.jsx
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
// filename: Hero.jsx
import { Subtitle, Title, Text } from "../utills/Basic.styled";     // ALSO DON'T FORGET TO IMPORT THIS WHEN YOU USE IT!!!
```

**Make this button**

![image](https://user-images.githubusercontent.com/116225566/228509872-08e3e53d-d9d4-4756-900e-7aa0791cd4e1.png)

```jsx
// filename: Basic.styled.jsx
const ProfileButton = styled.a`         // makes `a` tag
  display: inline-block;
  text-decoration: none;
  padding: 0.75rem 2rem;
  background-color: #f8f804;
  color: #252525;
  font-weight: 700;
  letter-spacing: 0.05em;
  border-radius: 0.25rem;
  cursor: pointer;
`;

export { Title, Subtitle, Text, ProfileButton };

```
```jsx
// filename: Hero.jsx
<ProfileButton href="#">Student Profiles</ProfileButton>
```

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

## Styling Component's Children

Here `img` tag is inside `div` tag. Both `div` and `img` tag can be styled at a time.

```jsx
const SchoolImage = styled.div`
  overflow: hidden;
  border-radius: 0.5rem;

  img {
    width: 100%;
  }
`;
```
and use this by the following way:

```jsx
   <SchoolImage>
      <img src={SchoolIMG} alt="school" />
   </SchoolImage>
```

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

## Using Pseudo-classes and Pseudo-elements

Let's say, we want to add a hover effect on our button. How can we do it?

```jsx
const ProfileButton = styled.a`
  display: inline-block;
  text-decoration: none;
  padding: 0.75rem 2rem;
  background-color: #f8f804;
  color: #252525;
  font-weight: 700;
  letter-spacing: 0.05em;
  border-radius: 0.25rem;
  cursor: pointer;
  opacity: 1;
  transition: opacity 0.5s ease-in-out;


  // this is the way
  &:hover,         
  &:focus-visible {
    opacity: 0.8;
    transition: all 1s ease-in-out;
  }
`;
```

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

## Applying Global Styles

CSS resets and other basic global styles can be applied by using helper function named `createGlobalStyle`. **[See Details...](https://styled-components.com/docs/api#createglobalstyle)**

```jsx
// filename: Global.styled.jsx
import { createGlobalStyle } from "styled-components";

const GlobalStyle = createGlobalStyle`
    *, ::after,::before{
        box-sizing: border-box;
        margin: 0;
        padding: 0;
    }

    body{
        font-family: 'Poppins', sans-serif;
        letter-spacing: 0.05em;
        font-weight: 400;
        background-color: aliceblue;
        color: #474547;
    }

    h1, h2{
        margin: 0;
        letter-spacing: 0.06em;
    }

    a{
        letter-spacing: 0.1em;
        text-transform: uppercase;
        display: inline-block;
    }
`;

export { GlobalStyle };
```

```jsx
// filename: App.jsx
import { GlobalStyle } from "./components/utills/Global.styled";

const App = () => {
  return (
    <>
      <GlobalStyle />           // Applying global styling........
      <Header />
      <Hero />
    </>
  );
};

```

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

## Adding Wrappers or Containers

![image](https://user-images.githubusercontent.com/116225566/228528440-f4402125-df71-40cf-857f-8b0fc20e0739.png)

```jsx
// filename: Containers.styled.jsx
import styled from "styled-components";

const MainWrapper = styled.div`
  max-width: 1440px;
  width: 90%;
  margin-inline: auto;
`;

const Card = styled.div`
  display: grid;
  grid-template-columns: 1fr 1fr;
  align-items: center;
  gap: 1rem;

  max-width: 1000px;
  margin-inline: auto;
`;

const Col = styled.div`
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 0.75rem;
`;

export { MainWrapper, Card, Col };
```

```jsx
// filename: App.jsx
 <GlobalStyle />
 <MainWrapper>
   <Header />
   <Hero />
 </MainWrapper>
```

```jsx
// filename: Hero.jsx
 <Card>
    <Col>
       <Title>Welcome To Student Database System.</Title>
       <Subtitle>One stop service for students</Subtitle>
       <Text>
         Lorem ipsum dolor sit amet consectetur minus exercitationem repellendus aut harum est doloribus aperiam!
         Cupiditate et quasi enim maiores neque?
       </Text>
         <ProfileButton href="#">Student Profiles</ProfileButton>
    </Col>
    <Col>
       <SchoolImage>
         <img src={SchoolIMG} alt="school" />
         </SchoolImage>
     </Col>
 </Card>
```
<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

## Media Query Features

```jsx
  const Card = styled.div`
  display: flex;
  justify-content: space-between;
  gap: 2rem;

  @media (max-width: 500px) {
    flex-direction: column-reverse;
  }
`;
```

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

# Learning Path: The Intermediate Part

In this interdemidate part, it will explain about extended styling, variables, props, polymorphic prop, and attrs features of Styled Components.

## Extending Styles

Let's say, we want to add another button, almost exactly identical to the remaining one but different bg-color. We can use `styled(<remaining-button>)` and thus extend the design by overriding.

```jsx
const ProfileButton = styled.a`
  text-decoration: none;
  padding: 0.75rem 2rem;
  background-color: #f8f804;
  color: inherit;
  font-weight: 700;
  border-radius: 0.25rem;
  cursor: pointer;
  margin-top: 2rem;
  transition: filter 0.5s ease-in-out;

  &:hover,
  &:focus-visible {
    filter: invert(1) brightness(150%);
    transition: all 0.25s ease-in-out;
  }
`;

const EnrollButton = styled(ProfileButton)`     // extends of `ProfileButton` and overrides css properties.
  background-color: #242222;
  color: #e7e7e7;
`;
```

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

## Applying Variables

Variables can be used as well.

```jsx
import styled from "styled-components";

const mediumSpacing = "2rem";

const VerticleSpacing = styled.div`
  margin-bottom: ${mediumSpacing};
`;

export { VerticleSpacing };
```

```jsx
const App = () => {
  return (
    <>
      <GlobalStyle />
      <MainWrapper>
        <Header />
        <VerticleSpacing />     // It is a `div` that holds `2rem` margin-bottom.
        <Hero />
      </MainWrapper>
    </>
  );
};
```

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

## Applying Props

One of the most powerful feature of styled-components is to use props which is completely unimaginable in normal css. Any javascript evaluated value can be passed as a props, making our dynamic styling easier. 

```jsx
const mediumSpacing = "2rem";

const VerticleSpacing = styled.div`
  /* margin-bottom: ${mediumSpacing}; */
  /* margin-bottom: ${(props) => (props.space ? props.space : mediumSpacing)}; */
`;
```

or,

```jsx
const mediumSpacing = "2rem";

const VerticleSpacing = styled.div`
  /* margin-bottom: ${mediumSpacing}; */
  margin-bottom: ${({ space }) => (space ? space : mediumSpacing)};         // by destructuring method !! 
`;
```

```jsx
<VerticleSpacing space="4rem"/>     // It is a `div` that holds `4rem` margin-bottom instead of `2rem` margin-bottom.
```

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

## Applying `as` Polymorphic Prop

```jsx
const MainWrapper = styled.main`
  max-width: 1440px;
  width: 90%;
  margin-inline: auto;
`;
```

Although the above component indicates a `main`tag, we can set this to a `footer` by the following way:

```jsx
 <MainWrapper as="footer">          //  using polymorphic props.
    <Text style={{ textAlign: "center" }}>Student Database System, All rights reserved @ 2023</Text>
 </MainWrapper>
```

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

## Applying `attrs`

```jsx
const Newsletters = styled.input.attrs((props) => {
  return { type: props.type || "text", size: props.size || undefined };
})`
  border-radius: 0.5rem;
  padding: 0.5rem 1rem;
  outline: none;
  border: 1px solid black;

  &::placeholder {
    color: red;
  }
`;
```

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

# Learning Path: The Advanced Part

- coming soon

## Theming

## Animations

<div align="right">
    <b><a href="#learn-styled-components">↥ back to top</a></b>
</div>

# Conclusion

All the essential things that need to be known to work with styled components are described. Therefore, now practice and implement the knowledge that you achieved. Use this article as a **cheat sheet.** Best of Luck.

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
