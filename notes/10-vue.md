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

3)
