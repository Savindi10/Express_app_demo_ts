1. initalize node 
>>> npm init -y 

2. install the package called express 
>>> npm install express

3. Dowload the dependancies 
>>>  npm install typescript ts-node @types/node @types/express --save-dev

4. Config typescript 
>>> npx tsc --init

5. Edit the file <tsconfig.json>
>>> 
{
  // Visit https://aka.ms/tsconfig to read more about this file
  "compilerOptions": {
    // File Layout
     "rootDir": "src",
    "outDir": "dist",

    // Environment Settings
    // See also https://aka.ms/tsconfig/module
    "module": "commonjs",
    "target": "es6",

    // Recommended Options
    "strict": true,
    "esModuleInterop": true,

  },
  "include" : ["src/**/*"],
  "exclude": ["node_modules", "dist"]
  
}

6. create folder called <src>
7. create <app.ts> file inside the src folder 

8. Edit the <package.json> file
{this create js file to run  and work on ts file}
>>> 
  "scripts": {
    "dev" : "ts-node src/app.ts",
    "build" : "tsc", 
    "start" : "node dist/app.js"
  },

9. create <app.ts> file 
>>> npm run build
{this create dist folder automatically , 
 inside this automatically add the compalired <app.js> file }

10. Edit app.ts file 
>>> 
import express, {Application} from "express";

const app:Application = express();

app.use(express.json());

app.get("/", (req, res) => {
    res.send("Hello World");
});

const PORT = 3000;
app.listen(PORT, () => {
    console.log(`Server is running on Port ${PORT}`);
});

11. Run the webapp 
>>>  npm run dev
{display this message when run : Server is running on Port 3000 }

12. Check the Browser
>>> type localhost:3000

13. 