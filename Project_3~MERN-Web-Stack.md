#### backend config

* updating and upgrading the machine
	`sudo apt update && sudo apt upgrade`
	![[Pasted image 20230317211824.png]]
	![[Pasted image 20230317211905.png]]

* get NodeJS from ubuntu repo
	`curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -`

	![[Pasted image 20230317212751.png]]

* install NodeJS using `sudo apt-get install -y nodejs`
	![[Pasted image 20230317213058.png]]

* checking installed version `node -v` and `npm -v`
	![[Pasted image 20230317213222.png]]

* make a project directory `mkdir todo`
![[Pasted image 20230317213409.png]]

* initialize the project using `npm init`
![[Pasted image 20230317213634.png]]

#### install ExpressJS
* `npm install express`
	![[Pasted image 20230317214019.png]]

* create an `index.js` file
	![[Pasted image 20230317214150.png]]

* installed libraries
	![[Pasted image 20230317214326.png]]

* Express code inside `index.js` file
	![[Pasted image 20230318102834.png]]

```javascript
const express = require('express');
require('dotenv').config();

const app = express()

const portNumber = process.env.PORT || 5000;

app.use((req, res, next)=>{
    res.header("Access-Control-Allow-Origin", "\*");
    res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type, Accept");
    next();
});

app.use((req, res, next)=>{
    res.send('Welcome to Express')
});

app.listen(port, ()=> {
    console.log(`Server running on port ${portNumber}`)
})
```

* allow traffic on port `5000` to ExpressJS Server
	![[Pasted image 20230318113256.png]]

* running the Express Server from CLI and moving the process to background
	![[Pasted image 20230318114526.png]]

* confirming connection via the browser on `port 5000`
	![[Pasted image 20230318114759.png]]
	![[Pasted image 20230318121058.png]]

* create routes for the api using `http methods` like `GET, POST, DELETE, PUT`
	![[Pasted image 20230318132416.png]]
```javascript
const express = require ('express');
const router = express.Router();

router.get('/todos', (req, res, next)=>{

});

router.post('/todos', (req, res, next)=>{

});

router.delete('/todos/:id', (req, res, next)=>{

});

module.exports = router;
```

* install mongoose
	![[Pasted image 20230318133934.png]]

* create models directory
	![[Pasted image 20230318134524.png]]

* testing backend code for database connection
	![[Pasted image 20230319013104.png]]

* testing `GET` method api via postman
	![[Pasted image 20230319052117.png]]

* testing `POST` method api via postman using raw json data 
	![[Pasted image 20230319052213.png]]

* backend api server listening on `port 5000`
	![[Pasted image 20230319052706.png]]

* testing `DELETE` method api via postman using raw json data 
	![[Pasted image 20230319053040.png]]
* install client side dependencies and proxy config
	![[Pasted image 20230319101003.png]]
* installing `concurrently and nodemon` as dev dependencies
	![[Pasted image 20230319054724.png]]
![[Pasted image 20230319054906.png]]

* running dev script using concurrently
	![[Pasted image 20230319060408.png]]
![[Pasted image 20230319060738.png]]
![[Pasted image 20230319061045.png]]
* install `axios http lib`
	![[Pasted image 20230319080536.png]]

* firewall config to allow traffic to `port 3000`
	![[Pasted image 20230319101707.png]]

* testing front-end app on `port 3000`
	![[Pasted image 20230319095420.png]]

* data from mongodb*
	![[Pasted image 20230319095834.png]]