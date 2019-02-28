# Create-react-app-craco-template
A template project that uses CRA with craco to adjust for the NAV infrastructure

## What this template does
By using this template or by following the guide bellow your project has support for:
 - Typescript
 - Less
 - Nav-frontend support
 - Zero downtime deploy with Create-React-App (CRA) setup*

## How to create this template
```
npx create-react-app my-app
cd my-app
npm install @craco/craco --save
npm install --save typescript @types/node @types/react @types/react-dom @types/jest
```

Then add typescript and less support to the project:
 - Rename `index.js` -> `index.tsx`
 - Rename `App.js` -> `App.tsx`
 - Rename `index.css` -> `index.less`
 - Rename `App.css` -> `App.less`

Add a craco.config.js in the root directory. The craco.config.js found in this project contains a setup that works for the NAV infrastructure

Lastly add the last craco packages and start the project:
```
npm install --save craco-less
npm install --save less-plugin-npm-import
npm start
```

## Notes
**Zero downtime deploy**: If you are using a nais image to run your front-end application. You must ensure that the file names are the same between each deploy. By default CRA always names the js file `[name].[file-hash].js` and the css file `[name]-[file-hash].css`. This is usually good, but we need the names to stay the same when serving static files from a nais application. If not, a user can end up getting a new index.html from a new running instance, but asking the old instance for the `js` and `css` files. If the filenames are different, the user will get a 404.

**Generated files**: When building typescript for the first time, CRA will create a `tsconfig.json` file and a `react-app-env.d.ts` file. `react-app-env.d.ts` will have the following content:
```
/// <reference types="react-scripts" />
```
You can read more about this syntax here: https://www.typescriptlang.org/docs/handbook/triple-slash-directives.html
