# MVC
<!-- NOTE order of process -->
View (User's Page/ index.html) => App.js => Router.js => Controller => Service => Models (AppState)

<!-- NOTE Description of order -->
View is what the user see's and interacts with. It is also the index.html (structure/ framework of a webpage).

App.js

Router.js controls the controller and what previews on the page (Also controls which page shows up if there is more than one page on the website i.e.; About info, Contact info, products etc ). The Router is an array of objects.

Controller's call and invoke functionality from the service, the controller cannot change any data in the AppState. Constructors are placed in the controllers.

Service is the middle man between the controller and it being in charge of functionality and changing the data available in the AppState. The Service cannot control or change the controller. This is also where your functions are made that the controller calls on when the page loads or the user interacts with the site.

Models (AppState) is where all the data on the website or user input data is stored and called on by the service when its needed to change. This is where the (export class NAME {constructor}) is placed. * only curly brackets, no parenthesis.

* All of these have to be imported and exported to the appropriate page in the order they process (i.e.; View <= Router (only when the page is changed will the router enact anything, otherwise the order skips over the router and connects straight to controllers.) <=> Controller <=> Service <=> AppState)

<!-- NOTE Notes-->
(Ctrl + D) allows you to search through the files with a search bar.

Always create the design/template in your index.html but then move it to the model and place it in a string so the controller can call the service that takes the model from the AppState and sends it up.

Under view folder you can create new views if your html is to long so that it doesn't crowd or take up a lot of lines of code in the router, which can be linked to the router to be called when someone switches to a new page:
 (i.e.; About page, Home page, Products page etc.)

getter function = used when drawing a template that you first design in index.html an then move to the folder designated to templates, all getters have to return something.

AppState is where you place your array's with objects and their values 
(i.e. stuff = {new something{name: place: etc}})

Inside model Name.js, this is where you make a export class:
 Name{ constructor(data){ this.something, this.something, this.something, etc}
 
 get ListTemplate(){
  return `<p class ="" onclick= "">${this.thing}</p>
 }}

In the services folder, make an:
export const  somethingSomething = new Something()

To create a draw function always make it separate from your classes. using '_'(underscore) is industry standard to denounce the nonvisible functions the user cannot see or interact with.

 A draw function looks like this:

function _somethingSomething(){
  const thing = Appstate.things
  let template = ''
  thing.forEach(thing => template += thing.template)
  setHTML ('thing-list', template)
}


This is an example of a listener: This would be placed in the controller and the empty string in the example is where a previously made id on your HTML is placed in the listener.

Appstate.on('', Appstate.something)


getters are good for making a new format for data you already have.

