# Steps

## 1. Init the project

```bash 
npm init
```

## 2. Install dev dependencies

```bash
npm i typescript @types/node tsx -D
```

## 3. Intall production dependencies

```bash
npm i fastify
```

## 4. Create `src` folder and `server.ts` file

## 5. On `server.ts` add the lines to create the server

```typescript
import fastify from 'fastify';
const app = fastify()

app.get('/', async () => {
  return "Hello World"
});

app.listen({
    port: 3333,
}).then(() => {
    console.log('Server running on port http://localhost:3333')
})
```

## 6. On `package.json` add the line to run the server

```json
"scripts": {
    "dev": "tsx watch src/server.ts"
  },
```

```bash
npm run dev
```

## 7. You can visualize the server running on port `http://localhost:3333` by your browser, or by terminal using HTTPie, or by Extensions on VSCode using REST Client

## 8. Install Prisma to manage database

```bash
npm i prisma -D
```

## 9. Init the prisma project and choose the database

```bash
npx prisma init --datasource-provider sqlite
```

## 10. On `prisma/schema.prisma` add the lines to create the tables of database
### On this project we will save the files on the disc but we can use Amazon S3 or Cloudflare R2 Docs

## 11. After create the tables, run the command to make the migrations

```bash
npx prisma migrate dev 
```

## 12. Visualize the database on Browser
  
```bash
npx prisma studio
```

## 13. Creating the routes
### 13.1 On `src`, create the folder `lib` and the file `prisma.ts`
### 13.2 On `prisma.ts` add the lines to connect with database
```typescript
import { PrismaClient } from '@prisma/client';
export const prismaClient = new PrismaClient();
```

## BONUS: Use `control` + `space` hotkeys on your device to search for a property or method

## 14. On `src`, create the folder `routes` to save every route separately

## 15. On `routes`, create the file `get-all-prompts.ts`

## 16. On `get-all-prompts.ts` import `FastifyInstance` from `fastify` and reference him on the function by `app`

## 17. Remove the same code from `server.ts` and paste on `get-all-prompts.ts`; OBS: Function must be `async`

## 18. On `server.ts` import the function `getAllPromptsRoute` from `get-all-prompts.ts` and call him by use `app` and `register` methods

## 19. Create the route `upload-video.ts` on `routes` folder
### 19.1 You can copy the code from `get-all-prompts.ts` and change the route and the methods

## 20. Create the route `upload-image.ts` on `routes` folder

## 21. Use Multer from Express or Multipart from Fastify to make the upload files

```bash
npm i @fastify/multipart
```

## 22. On `upload-video.ts` create all code to upload the video and treating the errors

## 23. Register the route on `server.ts` and test on `routes.http`; OBS: You can visualize the file save on database by Prisma Studio

## 24. Create the route `create-transcription.ts` on `routes` folder

## 25. Use Zod to validate the data

```bash
npm i zod
```

## 26. On `create-transcription.ts` create all code to create the transcription and treating the errors

## 27. Register the route on `server.ts` and test on `routes.http`; OBS: You can visualize the transcription save on database by Prisma Studio

## 28. Time to create the AI to make the transcription
### 28.1 We will use the API from OpenAI(just enter in the website and create an account to get the API KEY)
### 28.2 Paste the API KEY on `.env` file; OBS: You have to had $5 on your account to use the API
### 28.3 Install the package to use the OpenAI API

```bash
npm i openai
```

## 29. For the moment, node can't read local variables like `.env`, so we need to install the package `dotenv`

```bash
npm i dotenv -D
```

## 30. Create the http request to make the transcription

## 31. On `routes` create the `generate-ai-completion.ts` file to make the AI generate the transcription

## 32. Create the static params that make a route and after that, create the dynamic params that make the AI generate the transcription

## 33. Use `gpt-3.5-turbo-16k` to accepts more tokens(more expansive); The base one only accepts 4k tokens

## 34. Install `cors` to make the API access some of the frontend 

```bash
npm i @fastify/cors
```

## 35. Every frontend url will access my backend

```typescript
app.register(fastifyCors, {
  origin: '*'
})
```

## BACKEND HAS CONCLUDED 🥳🥳🥳

## Now let's start the  integration between frontend and backend!


