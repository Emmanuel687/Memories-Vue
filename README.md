Vue Framework/nuxt

Vue Resources
https://stlhorizon-my.sharepoint.com/:u:/g/personal/evance_stl-horizon_com/EYuWpp9Ou1ZHs5cK02_WU5oBATLxg3_lv0_2dwdqxSwsZA?e=4%3amQFEq0&fromShare=true&at=9

https://youtu.be/3B0ry4GI1cE?si=zoi033Ana8IrOt6y
https://youtu.be/mZFuR3-oNXQ?si=Hc2pvHXi_BEMLOyr

# UI/UX:- https://www.behance.net/

Vue RoadMap
1.Vue Introduction/Features
2.Vue Installation.
3.Vue Components.
4.Vue Binding
5.Vue Conditional Rendering
9.Vue Props
5.Vue List Rendering.
6.Vue Event Handling
7.Vue Computed Properties
8.Vue Directives
10.Vue Forms
Vue Introduction/Features
-Vue.js is a progressive Javascript framework used for building user interface.
-Some features of vue are:-
->Component based architecture enables creation of reusable components.
->Reactivity which enables automatic update of user interface when data changes.
->Use Directives to allow declarative rendering on the DOM, such v-if used for conditional rendering and v-for for rendering list.
->Lifecycle hooks such as create, mounted, updated and destroyed which are used in various stages of the lifecycle to perform actions.
NB:-Progressive means you can adopt and use Vue.js incrementally.

Vue Installation
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



Vue Components
Component Concepts
1.Vue Single component.
2.Vue Component Registration.

 Vue Single component
-A vue component is a  piece of code that can be reused within the application.
-A vue component is created with the .vue extension
-A vue component consists of three sections:template,script and styles which are optional.
-The template defines the HTML markup , you can use vue directives for dynamic behavior, event handling and data binding.
-The script defines the logic of the component where you write javascript and typescript code.
-A vue style script contains the component specific styles and scoped attributes ensures the styles is only applied to that particular component.

NB:-Script setup function is defined because we are using composition API.
      -Styles scope function is used to prevent styles to be shared globally.

Syntax
<template>HTML Markup</template>
<script setup> Javascript Logic </script>
<styles>Css Logic</styles>
Example
<template> <h1>{{vueApp}}</h1> </template>
<script setup>const vueApp = ref(“Hello Vue”)</script>
<styles> h1{ color:”#ffffff” } </styles>

Vue Component Registration
-Vue components can be imported and used across different components.
-Vue components can be imported in three ways , these are global component registration, local component registration and importing without registration.
-Global component registration is registered globally and can be used throughout the entire application.
-Local component registration is registered within the script of the component where it is supposed to be used.
-Components destination paths are imported in the script file of our vue file.
-Components are exported and then registered in a component method.

NB:- With setup on the script components are made available in the component.

Syntax
<template><myImportedComponent /></template>
<script setup>
import MyImportedComponent from ‘./components/MyImportedComponent’;
</script>

Syntax
<template><myImportedComponent /></template>
<script>
import MyImportedComponent from ‘./components/MyImportedComponent’;
export default{
      components:{MyImportedComponent, }
}
</script>

Example
<template><Header /></template>
<script setup>
import Header from ‘./components/Header’;
</script>

Example
<template><Header /></template>
<script>
import Header from ‘./components/Header’;
export default{
      components:{Header, }}
</script>


Vue Binding
Data Binding Concepts
1.Two Way Data Binding
2.One Way Data Binding

-Data binding is the process that establishes a connection between the data (model) and user interface (view) so that any changes made to one are automatically reflected in the other.

Two Way DataBinding
-Two way data binding allows data to flow in both ways from the model to the view and vice versa.
-When data changes in the model it automatically updates the view and when the user interacts with the view the changes are reflected back to the model, This is achieved using v-model directive
-The v-model directives is used to achieve two way data binding.
Example
<template>
<input v-model=”data” value=”data”/>
<span>{{data}}<span/>
</template>
<script>
  const data = ref(“”)
</script>
Output:-The V-model binds the  input field to message property and message property is updated in real time.

One way Data Binding
-One way data binding allows data to flow in a single direction, typically from the model to the view, Changes in the model update the view but changes in the view do not affect the model.
-The v-bind is used to dynamically bind an attribute to an expression.
-Some use cases of the v-bind is to bind the source of an image, binding links, binding class, style
Syntax
 v-bind:attribute=”expression”
 :attribute=”expression”
Example
<script>
    const image= “src/assets/images/photo.jpg”
    const alt = “Photo of a person”
    const link = “www.url.com”
</script>
<template>
      <img :src=”image” :alt=”alt” />
      <a :href=”link”/>
<template/>
Output:-v-bind binds the html attributes and when the expression changes the attribute is updated
Vue Conditional Rendering
-Conditional rendering in vue refers to the ability to conditionally show or hide elements in the user interface based on certain conditions.
-Vue directives such as v-if , v-else , v-else-if and v-show are used to achieve this.
-Vue v-if directive conditionally renders a condition if it's true.
-Vue v-else directive conditionally renders a condition if it's false.
-Vue v-else-if directive is used to check multiple conditions .
-Vue v-show conditionally renders an element but only toggles the visibility of an element without affecting its presence in the DOM.

NB:- v-if, v-else , v-else-if removes elements from the DOM.
       -v-show toggles element on the DOM without affecting its presence in the DOM.

Syntax
<HtmlElement v-if=”true-condition” > <HtmlElement />
<HtmlElement v-else-if=”false-condition” > <HtmlElement />
<HtmlElement v-else > <HtmlElement />

Example
<template>
       <h1 v-if=”showHeader”>Welcome to vue conditional rendering</h1>
       <p v-else=”showParagraph”>This paragraph is conditionally using v-else</p>
      <button @click=”handleHeader”>Toggle Header</button>
      <button @click=”handleParagraph”>Toggle Paragraph</button>
</template>

<script setup>
const showHeader = ref(true)
const showParagraph = ref(true)
const handleHeader =()=> showerHeader.value = !showHeader.value
const handleParagraph =()=>showParagraph.value = !showParagraph.value
</script>





Vue Props
Prop Concepts
1.Vue Properties
2.Vue Props Array Syntax
3.Vue Props Object Syntax
 
Vue Properties
-Props is a special keyword that stands for properties in Vue.js 
-Props is used to pass data from one component to another, primarily from parent to child component.
-Props are passed to a component then received on the other component, using the defineProps function in the setup script function.
-Props can carry various data types including Strings,Arrays,Objects,Booleans and even functions.
-Props data is binded using the v-bind directive to the component that receive props.
-Props data is received in the child component with the defineProps() in the composition API.
-The defineProps provides reactivity for props enabling automatic updates when prop values changes

NB:- Props should be binded when passed to various component levels.

Syntax
<template> 
     <ChildComponent :propName=”parentData”></ChildComponent>
</template>
Example
<template> 
     <ChildComponent :petName=”petName”></ChildComponent>
</template>
<script setup>
      const petName = ref(“Cat”)
 </script>



Vue Props Array Syntax 
-Props received by an array are defined using the defineProps.
-The array carries the name of the props received
-The prop variable could be destructured to extract individual prop values from the array.
Syntax
<script setup>
     const props = defineProps([“propName”, propName2])
     const [propName, propName2] = defineProps([“propName”, propName2])
</script>
Vue Props Object Syntax 
-Props received by an object are defined using the defineProps and their expected data types.
-Prop Data Types can be specified such as String, Array , Object , Boolean and Function.
-Object destructuring can be used to extract individual prop values from the object returned by defineProps.
Syntax
<script setup>
   const props = defineProps({propName:dataType})
   const props = defineProps({propName:{type:String, isRequired:true}})
</script>

<script setup>
   const {propName } = defineProps( {propName:dataType, propName2:dataType} )
   const { propName } = defineProps( { propName:{type:String }})
</script>

Vue List Rendering
-A List is used to display data in an orderly format.
-Vue list rendering involves displaying a collection of data in the form of a list.
-Vue offers several directives in order to render a list in the template for instance the v-for directive is used to iterate through an array or object and render the template for each item.

NB:-Key attribute is used to uniquely identify each item in the list.
       -Key attribute should be included when creating lists of elements.
       -Keys are used to identify items in a list that have changed, updated or deleted.
Syntax
<ul>
     <li v-for=”item in items>{{item}}</li>
     <li v-for=”{item ,i } of items :key=”i”>{{item}}</li>
</ul>
Example
<template>
<ul>
      <li v-for=”item of items :key=”item”>{item}<li>
<ul>
</template>

<script> 
import {ref} from “vue”
export default(){
  setup(){
     const items = ref([1, 2, 3r])
  return{items}
}}
</script>

Vue Event Handling
1.v-on Directive
2.Click Event
3.Submit Event
 v-on Directive
-Event listeners are used to handle users' interaction with the webpage such as clicking a button or hovering over a particular element.
-V-on directive is used for event handling with the name of the event you want to trigger.
-This event could be a click event, change event , submit event ,mouseenter event or mouseleave event. 
NB:-The shorthand for v-on event is @ 
Syntax
v-on:eventName
@eventName 

NB:-The @mouseenter is used to handle mouse enter.
      -The @mouseleave is used to handle mouse leaves.
      -The @change is used to handle input value changes.

Click Event
-The @click is used  to handle click events by listening to DOM events
-The handler function can be an inline handler or method handler
-The inline handler is used to execute simple logic.
-The method handler is used for complex logic.

Syntax
@click = “handlerFunction”

Example
<template>
    <span>{{count}}</span>
    <button @click=”count=count+1”>Add Counter</button>
    <button @click=”handleChangeItem>Change Item</button>
     
</template> 

<script setup>
const count = ref(0)
const item = ref(“Tie”)
const handleChangeItem = ()=> item.value=”socks”
<script/>

Submit Event
-The submit event is used to handle form submission in vue.js applications.
-The prevent event modifier is used to prevent the default behavior of a form submission
-The input value attribute in the input elements is not necessary when using the v-model as the v-model automatically binds the input value.
-A Conditional Statement is used to check whether both inputs are available, if either is missing the form submission won't occur.
-After the reactive object is created the input values are reset by setting them to an empty string as this clears the input fields for a new set of inputs.

NB:-The properties of the object should be accessed with the value 

Syntax
@prevent.submit = “handlerFunction”

Example
<template>
  <form @submit.prevent=”handleSubmit”>
      <input  v-model=”firstName” />
       <input v-model=”secondName” />
  <button type=”submit”>Submit</button>
  <form/>
<span>{firstName} {secondName}</span>
</template> 

<script setup>
if(!firstName || !secondName) return null
const firstName = ref(“”);
const secondName = ref(“”)
const handleSubmit = ()=>{
      const obj =reactive({
                   firstName:firstName.value,
                   secondName:secondName.value}})
firstName.value=””
secondName.value=””
<script/>








Vue Composition API
-Composition API is a new set of api introduced in Vue 3 to provide more flexibility and organization when writing Vue components.
-The composition API has the setup function, this is where you organize the component logic, the function is called before the component is created. 
-Composition API uses the refs and reactive objects, the ref is used  for individual values and reactive for complex objects.
-With the shorthand syntax we use the setup in the script tag and we don't need to declare to export , declare the setup function and also there is no need to return the object.
Syntax
<template><h1>{variable}<h1/></template>
<script>
import {ref} from vue
   export default(){
            setup(){
              const variable = ref(value)
              return{value}
             }
}
</script>

Syntax
<template><h1>{variable}<h1/></template>
<script setup>
import {ref} from vue
       const variable = ref(value)
}
</script>
Vue Reactivity
1.Vue Ref
2.Vue Reactive

-Reactivity is the ability for a framework to automatically track changes in data and update the user interface in response to the changes made.
-Ref and Reactive functions are used in composition API to manage reactivity.
-Ref and Reactivity provide a cleaner way to handle state and automatically update UI based on changes in data.
Vue Ref
-Ref function is used to create a reactive reference to a single value.
-Ref returns an object and the actual value can be accessed through the value property.
-The other property in ref is _v_isRef which is a boolean property that indicates whether the object is a ref. It is useful for the debugging process. 
NB:- Values declared with  are accessed with .value 

Syntax 
ref()
Example
const itemValue = ref(“Sock”)
itemValue.value = “Scurf”
console.log(itemValue.value)
Output:- Scurf
 Vue Reactive
-Reactive function is used to create reactive objects with multiple properties.
-Reactive function makes the entire object reactive rather than a single object.
-Reactive values are accessed directly.

NB:- Values declared with Reactive are accessed directly. 
Syntax 
reactive()

Example
const itemValues = reactive([{id:0,item:”Socks”},{id:1,item:”Jacket”}])
itemValues.at(1).item = “scurf” 
console.log(itemValues)
Output:- [{id:0,item:”Socks”},{id:1,item:”Scurf”}]


Vue Computed Properties
1.Computed Properties.
2.Computed Function.
3.Normal Function.
Computed Properties
-Computed properties are used to perform calculations on data and transform data which makes it easy to reuse the result on the template.
-Computed property automatically tracks its reactive dependencies, which means if any dependencies change computed property re-evaluates ensuring displayed value in the template remains upto-date.
-In Computed property vue automatically identifies reactive properties and if the reactive dependencies change the computed property is marked as dirty and vue re-evaluates it. 
-Computed Operations examples are such as filtering a list which transforms data, performing complex calculations and formatting date.
                                                       Computed Function
-A computed function is used to define computed properties in Vue components.
-A computed function takes in a callback function that returns the computed properties.
-Using Computed function is important to use when you need to perform calculations based on data that changes (reactive data),  automatic dependency tracking and caching for performance.

NB:-Caching is a mechanism used in computing to store and reuse previously computed or retrieved data which improves performance by avoiding overhead recalculation or refetching same data repeatedly.
Syntax
computed(()=>computed properties)

Example
<template>{{totalItem}}</template>
<script setup>
import {computed } from vue
const items = reactive([{item:”Socks”,quantity:3},{item:”Shirts”,quantity:5}])
const totalItem = computed(()=>items.reduce((acc,item)=>acc+item.quantity,0)
</script>
NB:-Computed Function
                                                       Normal Function
-Normal Functions can be used in cases where we are dealing with non-reactive logic or calculations that do not depend on Vue’s reactivity system.
-Normal function lacks the caching mechanism which the computed function has, this means the normal function recalculates its result even if the input values haven’t changed.
-Normal functions don't automatically track their dependencies hence if the function relies on reactive data changes to that data won't trigger automatic updates in the UI.
-Normal functions need manual dependency tracking to achieve reactivity.
Syntax
const functionName = ()=>{non-computed Operation}
Example
<template>{{modifiedValue}}</template>
<script setup>
const originalValue = ref(10)
const modifiedValue = ref(0)
const modifyValue = ()=>modifiedValue.value=originalValue*2;
</script>
NB:-Normal Function



Vue Forms

Syntax
<template>
  <form @submit.prevent=”handleSubmit”>
     <label>FirstName<input type=”text” v-model=”firstName”/></label>        
     <label>Age<input type=”number v-model=”secondName”/></label>        
</form>
</template>

<script setup>

const firstName = refs(“”)
const secondName = refs(“”)

        const handleSubmit = ()=>{

}
<script>



Vue APIs
1.Vue Composition API
2.Vue Option API

Vue Composition API 
-Vue composition api is a way of writing vue components using functions instead of option object.
Syntax 
<script setup>  </script>
<script>
  setup(){ }
  return{Data to be exposed to the Template}
</script>

Vue Optional API 

Syntax
<script>
   export default{
         data(){}
         methods:{}
         created(){} 

}
</script>



Vue Directives
Directives Concepts 
v-for
v-if
v-show
v-model

-Vue directives are special html element attributes that tell ue what to do with the DOM.
-Vue directives usually have a prefix of v-symbol and can be used to bind data and event listeners, control rendering of elements


Vue Emit
Parent
<template>
    <Child @handleEvent={handleEvent} />
</template>
<script setup>
       const handleEvent = (data)=>{
          console.log(data) }
</script>

Child
<template>

</template>
<script setup>
        const emit = defineEmit(handleEvent)
        emit(“handleEvent”, data)
</script>

