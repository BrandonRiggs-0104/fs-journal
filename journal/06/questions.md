# Single Page Applications with Vue
01. What is the entrypoint of an application?

  > | The entrypoint is the URL provided in the page and in an API. For example, '/' in a plain Vue folder would open up just the Home page. Or, '/about' would open up the About page, '/cars' would open the cars page etc.

02. What is the difference between a vue `component` and `page`?

  > | A component contains HTML, Java, and CSS that apply to just one component of an application while a page contains the same thing, but hosts components that users can interact with

03. What is ***Component-Based Architecture***?

  > | Component-Based Architecture is a model where each component in an application that would have several functions and/or API's connected to them are encapsulated away from each other. This allows for more UI, but has the problem of becoming over-engineered and bloated. However, it is very popular because of its ease of use for both developers and users.

04. What are the three tags that make up a Vue component?

  > | Template - This is the HTML tag section. script - This is the Javascript tag section. style - This is the CSS tag section.

05. What are ***lifecycle hooks***? What are lifecycle hooks used for?

  > | onMounted =  Run given block of code on page load, onUpdate = every time the page currently selected by the user is reloaded or refreshed it runs its given block of code, onUnmounted = Run given block of code when page is unloaded and another one loads.


06. Which component in Vue does the vue-router use to mount pages onto?

  > | Vue still uses router.js to run pages like a controller normally would. It also has a createRouter and loadPage which both help to open the page that we have connected with a path in the router. You can make these objects which may have one path that then branches into children depending on the page.

07. What is the difference between the `AppState` and the state object within a component?

  > | The AppState creates global variables that we can manipulate in different services. A state object is scoped exclusively to the vue component file it was made in.

08. What is the responsibility of `Services` in our Vue projects?

  > | Still the only thing that can change data in the AppState.

09. What are ***props*** and how are they used? Provide an example

  > | They are used to pass down data from a parent component to a child component. When we create a model in Node, we use props to let the API know to expect a String, Boolean, Number, etc. In Vue, we use :binding to restrict the data type.

10. What is the Vue method used to create watchable objects such as `state` or `AppState`?

  > | computed() creates listeners and emitters to watchable objects.
