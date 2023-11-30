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
```
"scripts": {
    ...
    "build": "tsc"
},
```
### Then run:
```
npx tsc --init
```
### Create tsconfig.json, paste this in:
```
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
