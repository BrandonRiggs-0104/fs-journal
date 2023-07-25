# Vue
// SECTION Day-1

1) To spin up your project you must use the start client and debug console. You don't have to re-spin your client when using vue. You also don't need to refresh while using vue to see the changes in your project.

2) When you say scoped in the scss style tag on the bottom of the page, that means the css styling will only affect what is located within the same file.

3) Inside the <script></script> tags you'll see what looks like a function, this area will act as your Javascript. If you want to inject Javascript into your HTML you must use double curly's {{Java in here}}.

4) Anything put inside the setup() is not accessible to the user, everything inside the return() is public and can be called from the HTML by the user. If you have something thats private but want it to become public just put it within the return().

5) Anything you want to be able to call from the HTML, such as a function like mining resources, you must make the function within the return()

6) To see your console log's, you now have to use logger.log().

7) ref takes an inner value and returns a reactive and mutable object, which has a single property .value that points to the inner value. i.e. let cheese = ref(0)

8) To bring in something from the Appstate into your return(), it must be imported and made to update the html by using the keyword computed. i.e. return(
  cheese: computed(() => {return AppState.cheese})
) <* NOTE If the computed only points to one variable then you don't need the curly brackets i.e. return(
  cheese: computed(() => return AppState.cheese)

9) models are still used in the same way with an export class Name{
  consurctor(data){
    this.etc = 
    this.etc = 
  }
}

10) Inside the AppState is where you'd build the upgrades and what they cost as well as the multiplier for resources gathered in the case of building uranium miner. For the auto upgrades you should put isTypeClick: false.

11) using the v-for="" inside a tag on the page acts like a for loop or forEach and will automatically upload everything in an array to the page.

12) : <*NOTE this is used for whats called data binding. 
13) :key <*NOTE the key kind of acts like an if.
14) @ <*NOTE instead on onclick you now would use @click, @submit. Then you can attach .prevent to the end like @click.prevent = "".

15) Putting a component inside the main vue page will insert all the given code inside the component. it should look like this: <NameofComponent />. It should be imported but it won't change font color to green, if it doesn't turn green then the import didn't work or never happened but the component still may work.

// SECTION Day-2

1) lifecycle hooks: onMounted, onUpdate, onUnmounted

2) Code within onMounted will be run when the vue updates and unMounted is all the code that will run when you leave your current page in vue.

// SECTION Day-3

1) The first thing that should always go inside a new function is a try/catch.

2) After making a model you should create a space to store the data your getting back and then you have to map out the data in the service. After mapping out the data you need to save th data to the AppState.

// SECTION week-7 day-1
// SECTION <* Backend information

1) Start by using express-vue for front end and back end. Once created immediately create a repository. Make sure your in the top folder, which means make sure you can see both the client and the server folders so they both get pushed to GitHub.

2) Make sure you set up your server, (.env) inside the client folder.

3) Start by making a schema: export const NameSchema = new Schema(). At the end of your new schema you need to place the timestamp: true toJSON: {virtuals: true} curly bracket thing outside the brackets for your actual schema. 

4) After making a new schema in the models folder, you have to update the dbcontext with the information of the schema.

5) Then you make a controller, make sure the first thing you put in after the constructor is super(''), then below it put this.router.

6) Under the this.router, you will make all your CRUD methods i.e.= Post, Get, Delete etc.

7) Once you have the method declared above, make your function within the curly brackets below.

8) New functions will always start with a try/catch. Don't forget in the params it always goes , (req, res, next) and the end always has a return.

9) After the function has been declared you need to create a service. Inside the service you will write the actual function. The first line will be to define a variable: newSomething = await dbContext.Something.create(somethingData).
Then you will always return the (somethingData) back to the controller.

10) //NOTE <* You only have to await a .populate() if its being used for a create function/.post().

// SECTION <* Frontend information

1) On the homepage, start with making a function that will retrieve the data inside the setup using the onMounted.

2) Create a Service file for the function you are creating on the homepage.

3) Inside the service, create a class and export it, this is also where you will write an async function to retrieve the data and matches the call of that function on the homepage.

4) Inside the onMounted, this is where you will put the function for it to be called.

5) After you successfully retrieve the data from the database, you need to make a class inside the models folder. i.e.= constructor(data){
  this.___ = data.____
}

6) After you created your model and you can successfully retrieve the data from the database, you need to create a space in the AppState that will allow you to save your data in the AppState.

7) Inside the service, you must use .map() over an array, if you have to drill into an object, then get to the nested array first and then use .map(). //NOTE <* This is how you save your data to your AppState.

8) After you successfully do that, do a raw data dump on the homepage {{ nameOfData }}

9) If you get a raw data dump then you are good to go, now you have to create a "template" on the homepage that shows how you want the data represented on the page. i.e.= cards

10) When setting a background img, the img should be placed in the App.vue body. This will allow it cover the navbar and footer. //NOTE <* You can get the saved img directory path by right clicking on it in vs code and click copy relative path and then reversing the backslash to forward slash.
//NOTE - <* You can use background img asset fixed to make the background stationary while the page

11) Inside the service, when setting up a prop, it should look like props: { nameProp: {type: string,array,object,etc, required: true}}

//SECTION week-7 day-2
//NOTE Frontend Information

1) Using beforeEnter: authSettled in the router will make sure all the authorization is completed and validated before sending a network request.

//NOTE Backend information

1) 