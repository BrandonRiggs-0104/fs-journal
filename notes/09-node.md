# Node

1) To get started make a new controller under server

2) Still start with export class ___Controller

3) All controllers inherit by using ____Controller extends BaseController

4) The new controller has to have a super('api/___') call to bring in all the data and baseUrl from the inherited controller, this is called a mount path

5) After the super() call place this.router, almost all of your controllers are going to start with the previous 4 steps.

6) Then use .get('',this.___) The this.___ will be what method you are using to run when someone make a request. 

7) Every single method you write inside a controller with start with methodName(req, res, next). Req = Request, Res = Response, Next = The next thing that happens.

8) When first making a method always start with;
 methodName(req, res, next){
  try {
    res.send({message: 'You made a request!'})
  }
  catch(error){
  next(error)
  }
 }

9) After you make a change you will always have to respin your server (little green button in the VsCode dev tools)

10) Inside server > db > this is where you can make a fake database to practice.

11) When first accessing a method start with;
 async methodName(req, res, next){
  try {
    const ___ = await ___Service.get___() <* method name
    res.send(___)<* inside the parenthesis put in the name of the data you are accessing.
  }
  catch(error){
  next(error)
  }
 }

12) Under the this.router
.get('',this.get__)
.get('/:id', this.get___byid) <* anything with a forward slash inside of quotes the system will recognize it as data provided by the user such as an id. This is also going to be the params down in the method.

13) To activate debug you need to put a breakpoint by clicking the red dot to the let of the code line. <* All debugging will be done in VsCode rather than the webDev tools.

14) When allowing users to post to your api, always put your parameters as async ____(req, res, next) followed by a try/catch.

// SECTION day-2 //

1) Make sure to open in workspace, it should only contain a client folder and a server folder.

2) When filling out the .env file, go to Mongodb and click connect and grab the connection string and copy and paste it into the .env CONNECTION_STRING. 

3) To fill out Auth requirements go to auth0 and click applications and click myapp and copy and paste my domain, client id. Under the api tab you can find the api audience next to the api you created. Then copy and paste the AUTH information from .env to env.js.

4) Inside the model, when exporting it on the bottom it will go like export const ___Schema = new Schema({
  make: {type: ___, required: true, maxlength: __, minlength: __},
  model: {}
}) <* Everything in the parenthesis is what information is allowed to be entered into your database.

5) Copy and paste timestamp info from value.js in the end of your model inside the parenthesis.

6) Inside dbContext, this is where you are going to put you collectons i.e.:
Cars = mongoose.model('car', CarSchema)

7) To make someone authorized to post in the database, put .use(Auth0Provider.getAuthorizedUserInfo). Inside of postman you have to open the authorization tab and make sure you delete the info provided and replace it with you actual bearer token by accessing the network tab under webdev tools and copy the bearer token under payload. <* This is only needed IF a user is trying to add, change or remove data from the database.

8) 