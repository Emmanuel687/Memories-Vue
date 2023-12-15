
https://stlhorizon-my.sharepoint.com/:u:/g/personal/evance_stl-horizon_com/EYuWpp9Ou1ZHs5cK02_WU5oBATLxg3_lv0_2dwdqxSwsZA?e=4%3amQFEq0&fromShare=true&at=9

https://component-party.dev/

# Vue Introduction/Features
-Vue.js is a progressive Javascript framework used for building user interface.
-Some features of vue are:-
->Component based architecture enables creation of reusable components.
->Reactivity which enables automatic update of user interface when data changes.
->Use Directives to allow declarative rendering on the DOM, such v-if used for conditional rendering and v-for for rendering list.
->Lifecycle hooks such as create, mounted, updated and destroyed which are used in various stages of the lifecycle to perform actions.
NB:-Progressive means you can adopt and use Vue.js incrementally.

# Vue Installation
-Vue project can be installed using Content Delivery Network (CDN) or Using Vue Command Line interface.(CLI)
-Vue CDN is suitable for small projects compared to Vue CLI which is required for complex project and for development environment.
-To create a vue project make sure node.js is installed on your computer.
-To install a new project run npx create-vue @latest name-of-project on the terminal
-To start the project run npm run dev.

NB:-Note to install all dependencies using npm install

Syntax
npx create-vue @latest <Project name>
npm install
npm run dev
Example
npx create-vue @latest expense-tracker


# Vue Components
Component Concepts
1.Vue Single component
2.Vue Component Registration.

Vue Single component
-A vue component is a small piece of code that can be reused within the application.
-A vue component is created with the .vue extension
-A vue component consists of template , script and styles which is optional which is in a single file.
-A vue template represents the HTML markup that defines the structure of the component,with the template you can use vue directives for dynamic behavior, handle events and bind data using double curly braces.
-A vue script represents the section where we can write javascript and typescript logic of a component, with the script we define the setup function and return data object.
-A vue style script contains the component specific styles and scoped attributes ensures the styles is only applied to that particular component.

NB:- Setup replaces the option API for defining reactive data, methods and lifecycle behaviors.


Syntax
<template><HtmlElement></HtmlElement></template>
<script>
     setup(){}
     return{}
</script>
<styles>Css Logic</styles>
Example
<template>
    <h1>{{}}</h1>
    <button @click=”increment”>Increase</button>
</template>

<script>
    setup(){
      export default(){
        const title = ref(“Vue);
        const increment =()=>title.value = “Incremented”;
       }

       return{title,increment }
        }
</script>

<styles>
    h1{ color:blue}
</styles>




Vue Components
Component Concepts
1.Vue Single component
2.Vue Component Registration.

 Vue Single component
 -A vue component is a small piece of code that can be reused within the application.
-A vue component is created with the .vue extension
-A vue component consists of template , script and styles which is optional which is in a single file.
-A vue template represents the HTML markup that defines the structure of the component,with the template you can use vue directives for dynamic behavior, handle events and bind data using double curly braces.
-A vue script represents the section where we can write javascript and typescript logic of a component, with the script we define the setup function and return data object.


