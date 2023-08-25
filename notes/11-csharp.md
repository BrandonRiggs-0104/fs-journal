# CSharp

//SECTION Week-10 Day-1 C# Intro

1) To start, in your command line type in dotnet new console. This will create the files you need to write in c#.

2) To print to the console, pull up the terminal inside VSCode and type in dotnet run. Console.WriteLine("") is the code to print to the console log.

3) To build a string you have to use "" (double quotes) with a semi colon on the end (;).

4) To string interpolate the $ now has to be on the outside of the double quotes. Console.WriteLine(${"example"})
  Ex:
  string firstName = "Brandon";
  char middleInitial = "E"
  string lastName = "Riggs"
  Console.WriteLine($"Hello my name is {firstName} {middleInitial} {lastName}")

  5) To create a number variable, you have to use int num = 3. C# you always have to declare what type of variable first before you can assign it a value.

  6) You can use double halfNum = 2.5, the double means it will go out to 2 decimal points.

  7) To add two things together in the console log use this example
    Ex:
    int num = 3
    double halfNum = 2.5
  Console.WriteLine(num + halfNum)

  8) To create a boolean you have to declare it first by saying bool.
  Ex:
    bool brandonLikesCats = true

//NOTE This does log correctly

  if(brandonLikesCats){
    Console.WriteLine("Of course this is true");
  }

//NOTE This doesn't work because its not true.

  if(firstName == "Ellie"){
    Console.WriteLine("My Name is Ellie")
  }

  if(total > 2){
    Console.WriteLine("Total was greater than 2")
  }

9) To create an array use this example. Arrays in C# cannot have variables within the array taken out or changed and anything you add to the array has to match what type of variable you declared when making the array.

Ex:
  int [] numbers = {1,2,3,4,5};

To write a for loop for the array created above use this example.
Ex:
 for(int i = 0; i < numbers.length; i++)
 {
  int number = numbers[i]
  Console.WriteLine(number)
 }

10) To build a class in C# you can use this example.
  Ex:
List<string> names = new List<string>();

names.Add("Ellie")
names.Add("Shelby")
names.Add("Astro")
names.Add("Grizzly")

11) To write a foreach that goes through everything in an array you can use this example.
  Ex:
foreach(string in names)
{
  Console.WriteLine($"My name is {name}")
}

//SECTION Week-10 Day-1 Building a small api

1) Using the command line, run bcw create, and use the dotnet-auth to create the template.

2) When creating a class in the models page it has to be set up like this
  ex:
public class cat
{
  //NOTE public = declaring who has access to this class. string = declaring what type of data it will be. { get; } is stating what can be done with the data, can even write get functions in the class per param/argument. { set; } is stating what can be done with the data, can even write functions that allow you to set/change the data. { get; set; } can be used together as well.

public string Name {get; set}

public int Age {get; set;}

public bool HasTail {get; set;}

public double NumberOfLegs {get; set;}
}

//NOTE constructor

public Cat(string name, int age, bool hasTail, double numberOfLegs)
{
Name = name;
Age = age;
HasTail = hasTail;
NumberOfLegs = numberOfLegs;
}

3) When setting up a controller it will look like this.
  Ex:
[ApiController]
[Route("api/[controller]")]

public class CatsController : ControllerBase
{
[HttpGet] <- //NOTE This applies to only the first method that comes after it.

public string Test()
{
  return "test worked!"; <- //NOTE every statement has to end with the (;)
}
//NOTE to connect a controller to a service it has to start with private, this means only that controller has access to that service.

private readonly CatsService _catsService;
public CatsController(CatsService catsService)
{

}
}

4) Setting up a get function

[HttpGet]
public ActionResult<List<Cat> GetCats() //NOTE ActionResult allows you to get the Http responses back, Ok() and BadRequest() are forms of an Http response.

{
try{
  List<Cat> cats = cats;
  return Ok();
}

Catch (Exception e)
{

  return BadRequest(e.Message);
}
}

5) This is how to set up a new Service.
  Ex:
public class CatsService{
private readonly CatsRepository _CatsRepository;

internal List<Cat> GetCats()
{
List<Cats> cats= _catsService.GetCats();
return cats;
}
}


6) This is how to set a repository
 Ex:
public class CatsRepository
{
  private readonly List<Cat> cats = new List<Cat>();

  internal List<Cat> 
}

//NOTE 
SQL EMAIL: kowifix761@vreaa.com
//NOTE

//SECTION Week-10 Day-2 Working with SQL

1) Go to dbSetup.sql and hit execute. This will create an account table in your database.

2) Below you need to start with:
CREATE TABLE tableName(
  id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(10) NOT NULL COMMENT 'naming whatever',
  ownedByGrandma BOOLEAN DEFAULT true COMMENT 'keeps track of if thing was owned by grandma using a true false statement'
  birthday DATE NOT NULL,
  applesEaten SMALLINT UNSIGNED DEFAULT 0
) default charset utf8 COMMENT '';

Then press execute to create the new table.

3) If you need to add anymore information or values to a table that you've already created, do this:

INSERT INTO
tableName (name, ownedByGrandma, birthday, applesEaten)
VALUES ('name', true, 1998-10-01, 1000)
//NOTE values added have to be in the same order as its written in the parenthesis on the tableName line.

//SECTION Week-10 Day-2

1) First build your model:
public class car
{
  public in Id (get; set;)
  public string Make (get; set;)
  public string Model (get; set;)
  public string Color (get; set;)
  public int Year (get; set;)
  public double Price (get; set;)
  public bool ownedByGrandma (get; set;)
}

2) Then build your controller:
[ApiController]
[Route ("api/[controller]")]

public class CarsController : ControllerBase

[HttpGet]

public ActionResult <List<Car>> GetCars(){
try()
catch()
}


3) The third step is to create your service:

public class CarsService





4) After your service is set up, you have to create a repository. 
//NOTE the repository is the only thing that should be talking to your database, you will have to make a connection from the repository to the database.

Ex:
private readonly IDbConnection _db;

//SECTION Week-10 Day-3

1) First thing you do is setup your appsettings.Development.json, should have that info slacked to yourself from previous projects.

2) The second thing you need to do is fill out your env.js with the credentials that you also slacked to yourself for auth0. Make sure you check what port your going to be spinning up on in your env.js and add the 's' to the end of the http portion.


3) Make sure you have gone to the server side and run the create account table in the dbSetup.sql, it should already be created but just re-run the execute to double check.

4) After you have your tables created on the server side you have to then create a model on the front end.

5) After you have made a model, the next step is to go and write a controller.

6) After you create the controller you will have to go and create a service when you write your first request(i.e. get, post, etc)
//NOTE remember that services are a class!

7) After you create a service it has to then be connected to a repository. 
//NOTE remember that repositories are a class!

8) Then make sure you go to startup.cs and connect your new repository as well as your new service so they can be injected when they are needed.
//NOTE Make sure you update your startup every time you create a new table

9) Make sure to create a new table for every different data type (i.e. Albums, Pictures, Homes, Cars, etc..)

//SECTION - week 11 full stack example before final.
//NOTE Steps on creating a fullstack-app.

1) start with bcw create, use dotnet.vue

2) After the project is created open it in the workspace.

3) Once it's open, make sure your database is connected, then setup the appsettings.deveopmnt.json and the env.js with the information you slacked yourself. Also mak sure you update the base url so its not localhost 3000 an change it into localhost 7045.

4) Once the setting and env is setup start your server and client end using the debug category on the right hand side of the screen. 

5) Using the UML provided, go to dbsetup, create a table and then execute it to create one in your database.
//NOTE If you need the createdAt or updatedAt copy and paste it from the aaccounts table provided already.

6) After the tables have been established, create the model, right click and do new C#, class, name of class.

7) Fill in the properties that are on your table in the dbSetup.

8) Next move onto controller, right click and select new C# controller.

9) Then create a Service for your new controller

10) then create a repository for your new service and controller.

11) After all that is created go to startup and make sure you put in your new repository and service.

12) Then start your post function in your controller, always start with [HttpPost] and [Authorize] (order of them doesn't matter).

13) Always use a try catch to start with, catch will always be e.message and return a BadRequest(e.message).

14) When using authorize 

15) In the service, make a function for creating/post.

16) Do the same thing for your repository by making a function for creating something.
//NOTE if you are getting back an id, use ExecuteScalar at the end of your repository.

18)  Don't forget that after you write and save any code at this point you will have to respin your server everytime.

19) After you've created the post functions and they have been tested and you ca successfully create whatever then repeat the same steps again for [HttpGet].
//NOTE when returning with an actionResult make sure you use Ok(whatever).

20) Go to Account, add : Profile to the end of class Account. Then create a public class with the name of Profile.

//SECTION Moving to front end afetr creating a post, get it all, and get by id

21) In the homepage, create an async function to get your thing. Then create a service and make the function to get whatever you are trying to get.

22) In your homepage, start with a try catch

23) In your service, create a function to get whatever your wanting from your database.

24) after you are able to console log all the things your trying to get from your database, You have to create a model with constructor(data).

25) After your model has been setup you need to go to your appstate and create a place for your data to be saved

26) Back on the homepage, to get data to be dumpable, use the {{}} then in the return make sure you do a computed for all the data.

27) 