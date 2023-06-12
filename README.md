# TODO

# Development Description

-   Create a new project Todo with `mkdir todo && cd todo`
-   create README.md
-   initialize git with `git init`
-   create .gitignore
    -   node_modules/
    -   dist/
    -   .env
    -   .parcel-cache

## Frontend

-   mkdir `frontend` && cd `frontend`
-   initialize npm with `npm init`
-   initialize typescript with `tsc --init`
-   install dependencies
    -   Devdependencies
        -   `npm i -D parcel typescript @types/react @types/react-dom`
    -   Dependencies
        -   `npm i react react-dom`
-   update package.json

    ```json
    {
        "main": "index.html", // delete this line
        "source": "index.html",
        "scripts": {
            "start": "parcel",
            "build": "parcel build"
        }
    }
    ```

-   update tsconfig.json

    ```json
    {
        "compilerOptions": {
            "target": "es2016",
            "jsx": "react-jsx",
            "module": "commonjs",
            "forceConsistentCasingInFileNames": true,
            "strict": true,
            "noImplicitAny": true,
            "strictNullChecks": true,
            "skipLibCheck": true,
            "esModuleInterop": true
        }
    }
    ```

-   create index.html
-   create working structure

    ```
    - frontend
        | - src
        |   | - components
        |   | - config
        |   | - pages
        |   | - utils
        |   | - App.css
        |   | - App.tsx
        |   | - index.tsx
    ```

## Backend

-   mkdir `backend` && cd `backend`
-   initialize npm with `npm init`
-   initialize typescript with `tsc --init`
-   install dependencies
    -   Devdependencies
        -   `npm i -D nodemon typescript tslint @types/express @types/node @types/cors`
    -   Dependencies
        -   `npm i express mongoose dotenv cors`
-   update package.json

    ```json
    {
        "main": "dist/server.js",
        "scripts": {
            "prebuild": "tslint -c tslint.json -p tsconfig.json --fix",
            "build": "tsc",
            "prestart": "npm run build",
            "start": "node .",
            "dev": "nodemon ."
        }
    }
    ```

-   update tsconfig.json

    ```json
    {
        "compilerOptions": {
            "target": "es2016",
            "module": "commonjs",
            "esModuleInterop": true,
            "forceConsistentCasingInFileNames": true,
            "strict": true,
            "noImplicitAny": true,
            "strictNullChecks": true,
            "skipLibCheck": true,
            "moduleResolution": "node",
            "sourceMap": true,
            "outDir": "./dist",
            "rootDir": ".",
            "baseUrl": "./"
        },
        "include": ["src/**/*.ts", "server.ts"],
        "exclude": ["node_modules/**/*", "dist"]
    }
    ```

-   Set tslint.json

    ```json
    {
        "defaultSeverity": "error",
        "extends": ["tslint:recommended"],
        "jsRules": {},
        "rules": {
            "trailing-comma": [false],
            "no-console": [true, "warning"]
        },
        "rulesDirectory": []
    }
    ```

-   set nodemon.json

    ```json
    {
        "ignore": [".git", "node_modules", "dist"],
        "watch": ["."],
        "exec": "npm start",
        "ext": "ts"
    }
    ```

-   create server.ts
-   create backend structure

    ```
    - backend
        | - src
        |   | - config
        |   | - controllers
        |   | - interfaces
        |   | - models
        |   | - routes
        |   | - utils
        | - server.ts
    ```

# Resources

-   [Design Resource](https://dribbble.com/shots/15185058-Collection-Tasks)
-   [Working Demo](https://siddastic.github.io/svelte-todo/)
