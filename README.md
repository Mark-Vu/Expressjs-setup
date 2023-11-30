# Expressjs-setup

This guide walks you through setting up a basic Express.js application using TypeScript.

## Prerequisites
Ensure you have [Node.js](https://nodejs.org/) installed on your machine.

## Setup Instructions

### Initialize your project
First, create a new directory for your project and initialize it with npm:

```
mkdir expressjs-project
cd expressjs-project
npm init --yes
npm install -D typescript ts-node-dev @types/express @types/cors @types/node dotenv nodemon express cors 
```

### In package.json:
```json
"scripts": {
    "build": "tsc",
    "start": "node dist/index.js",
    "dev": "nodemon src/index.ts"
  },
```
### Then run:
```
npx tsc --init
```
### Create tsconfig.json, paste this in:
```json
{
  "compilerOptions": {
    "module": "NodeNext",
    "moduleResolution": "NodeNext",
    "target": "ES2022",
    "sourceMap": true,
    "outDir": "dist",
  },
  "include": ["src/**/*"]
}
```

### Create and go under "src" folder
```
mkdir src
cd src
```

### Create index.ts under src folder:
```javascript
import express, { Express, Request, Response , Application } from 'express';
import userRouter from './user/routes';

const app: Application = express();
const port = process.env.PORT || 8000;


app.use('/user', userRouter);

app.get('/', (req: Request, res: Response) => {
  res.send('Welcome to JobHub');
});

app.listen(port, () => {
  console.log(`Server is running at http://localhost:${port}`);
});
```

### Create folder "user" and inside /user/routes.ts:
```javascript
import express, { Request, Response, Router } from 'express';

const userRouter: Router = express.Router();

userRouter.get('/users', (req: Request, res: Response) => {
  res.send('This is user route');
});

export default userRouter;
```
