TypeScript is a superset of JavaScript, meaning that it does everything that JavaScript does, but with some added features.

The main reason for using TypeScript is to add **static typing** to JavaScript. Static typing means that the type of a variable cannot be changed at any point in a program. It can prevent a LOT of bugs!

- TypeScript cannot be understood by browsers, so it has to be compiled into JavaScript by the TypeScript Compiler (TSC)

### Setting up a TypeScript Project
To install TypeScript globally on your machine:
```bash
npm i -g typescript
```
To install TypeScript locally on your project:
```bash
npm i typescript
```
But, while I was install TypeScript in my machine having Ubuntu 22 the above command didn't worked for me. Instead, I had to run the following command which installed TS globally on my machine:
```bash
sudo apt install node-typescript
```

### How to Compile TypeScript
Create a file **index.ts**:
```ts
let sport = 'football';
let id = 5;
```
To compile down the above TS code into JS:
```bash
tsc index
```
TSC will compile the code into JavaScript and output it in a file called **index.js**:
```js
var sport = 'football';
var id = 5;
```
If you want to specify the name of the output file:
```bash
tsc index.ts --outfile file-name.js
```
If you want TSC to compile your code automatically, whenever you make a change, add the "watch" flag:
```bash
tsc index.ts -w
```
**NOTE: An interesting thing about TypeScript is that it reports errors in your text editor whilst you are coding, but it will always compile your code – whether there are errors or not.**
This is an important property of TypeScript: it assumes that the developer knows more.

### How to Set Up the ts config File
The ts config file should be in the root directory of your project. In this file we can specify the root files, compiler options, and how strict we want TypeScript to be in checking our project.

First, create the ts config file:
```bash
tsc --init
```
You should now have a `tsconfig.json` file in the project root.

Here are some options that are good to be aware of (if using a frontend framework with TypeScript, most if this stuff is taken care of for you):
```json
{
    "compilerOptions": {
        ...
        /* Modules */
        "target": "es2016", // Change to "ES2015" to compile to ES6
        "rootDir": "./src", // Where to compile from
        "outDir": "./public", // Where to compile to (usually the folder to be deployed to the web server)
        
        /* JavaScript Support */
        "allowJs": true, // Allow JavaScript files to be compiled
        "checkJs": true, // Type check JavaScript files and report errors
        
        /* Emit */
        "sourceMap": true, // Create source map files for emitted JavaScript files (good for debugging)
         "removeComments": true, // Don't emit comments
    },
    "include": ["src"] // Ensure only files in src are compiled
}
```
To compile everything and watch for changes:
`tsc -w`
Note: when input files are specified on the command line (for example, `tsc index`), `tsconfig.json` files are ignored.

