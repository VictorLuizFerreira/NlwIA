# Steps

## 1. Install and run Vite
   
   ```bash
   npm create vite@latest
   npm i
   npm run dev
   ```
   
## 2. Cleaning the code

### 1. On `index.html`, change the title and remove the `logo.svg` file and its import;
### 2. Delete the `.eslintrc.cjs` file;
### 3. Delete the `assets` folder; 
### 4. On `src`, remove `App.css`; 
### 5. On `App.tsx` remove all content in `return` and add a `<h1>Hello World</h1>`, remove all importations and create `export function app()`;
### 6. On `main.tsx` add `import { app } from './App';`;
### 7. On `index.css` remove all content;
### 8. On `public` remove `vite.svg`;

## 3. Make the first git commit

```bash
git init
git add .
git commit -m "Initial commit"
```

## 4. Install and configure shadcn/ui

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```
### On `tsconfig.json`, add the following lines:
```json 
/* paths */
"baseUrl": ".",
"paths": {
  "@/*": ["./src/*"]
}
```

## 5. # Import types/node so you can import "path" without error

```bash
npm i -D @types/node
```

## 6. # On `vite.config.ts`, import path add the following lines

```ts
resolve: {
    alias: {
      "@": path.resolve(__dirname, "./src"),
    },
  },
```

## 7. Run the client of shadcn/ui

```bash
npx shadcn-ui@latest init
```

## 8. Start the shadc/ui project

```bash
npx shadcn-ui@latest add button
```   

## 9. On `index.css` remove .dark{} and add the stiles that you like

## 10. Customize your page on `App.tsx`

## 11. Install Lucide Icons

```bash 
npm i lucide-react
```

## 12. Add Shadcn-UI components on your app

```bash
npx shadcn-ui@latest add {name of component}
```

## FRONTEND HAS CONCLUDED 🥳🥳🥳
## Now let's start the backend!

