#### backend config

#### updating and upgrading the machine

`sudo apt update && sudo apt upgrade`
![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317211824.png)
![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317211905.png)

#### get NodeJS from ubuntu repo

`curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -`

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317212751.png)

#### install NodeJS using `sudo apt-get install -y nodejs`

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317213058.png)

#### checking installed version `node -v` and `npm -v`

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317213222.png)

#### make a project directory `mkdir todo`

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317213409.png)

#### initialize the project using `npm init`

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317213634.png)

#### install ExpressJS

#### `npm install express`

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317214019.png)

#### create an `index.js` file

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317214150.png)

#### installed libraries

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317214326.png)

#### Express code inside `index.js` file

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230318102834.png)

```javascript
const express = require("express");
require("dotenv").config();

const app = express();

const portNumber = process.env.PORT || 5000;

app.use((req, res, next) => {
  res.header("Access-Control-Allow-Origin", "####");
  res.header(
    "Access-Control-Allow-Headers",
    "Origin, X-Requested-With, Content-Type, Accept"
  );
  next();
});

app.use((req, res, next) => {
  res.send("Welcome to Express");
});

app.listen(port, () => {
  console.log(`Server running on port ${portNumber}`);
});
```

#### allow traffic on port `5000` to ExpressJS Server

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230318113256.png)

#### running the Express Server from CLI and moving the process to background

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230318114526.png)

#### confirming connection via the browser on `port 5000`

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230318114759.png)
![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230318121058.png)

#### create routes for the api using `http methods` like `GET, POST, DELETE, PUT`

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230318132416.png)

```javascript
const express = require("express");
const router = express.Router();

router.get("/todos", (req, res, next) => {});

router.post("/todos", (req, res, next) => {});

router.delete("/todos/:id", (req, res, next) => {});

module.exports = router;
```

#### install mongoose

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230318133934.png)

#### create models directory

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230318134524.png)

#### testing backend code for database connection

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319013104.png)

#### testing `GET` method api via postman

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319052117.png)

#### testing `POST` method api via postman using raw json data

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319052213.png)

#### backend api server listening on `port 5000`

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319052706.png)

#### testing `DELETE` method api via postman using raw json data

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319053040.png)

#### install client side dependencies and proxy config

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319101003.png)

#### installing `concurrently and nodemon` as dev dependencies

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319054724.png)
![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319054906.png)

#### running dev script using concurrently

      ![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319060408.png)

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319060738.png)
![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319061045.png)

#### install `axios http lib`

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319080536.png)

#### firewall config to allow traffic to `port 3000`

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319101707.png)

#### testing front-end app on `port 3000`

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319095420.png)

#### data from mongodb\####

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319095834.png)
