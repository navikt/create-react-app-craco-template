# Create-react-app-craco-template
A template project that uses CRA with craco to adjust for the NAV infrastructure

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

Then
```
npm install --save craco-less
npm install --save less-plugin-npm-import
npm start
```
