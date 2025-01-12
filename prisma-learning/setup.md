## Node Express TypeScript Setup
- `npm init -y`
- If using volta `volta pin node@22.12.0`
- `npm i -D typescript`
- `npm i express`
- `npm i -D @types/express @type/node`
- Change `type = module` in package.json
- `npx tsc --init` - For tsconfig.json
- Make the following changes
  - Change the module to "ES6"
  - Un-comment "rootDir" and change the value to "./src" as all of our code is in src folder.
  - Un-comment "outDir" and change the value to "./dist" - Here all the transpiled code will be generated.
  - Change the following to leverage the effectiveness of typescript : "noImplicitAny": true, "strictNullChecks": true, "strictFunctionTypes": true,
- `npm i -D nodemon`
- **Build Script**: `tsc --build`
- **Start Script**: `node ./dist/index.js`
- **Dev Script**: `tsc && nodemon ./dist/index.js`
- Add `.gitignore` with `.env` and `node_modules` hidden.

## Prisma Setup with Postgres
 
### First, install the required dependencies:
- `npm install @prisma/client`
- `npm i -D prisma`
- `npx prisma init --datasource-provider postgresql` 
  - This will create a `prisma` folder with a file `schema.prisma`
  - This will also create a `.env` file with `DATABASE_URL` property.

### Creata a Database using POSTGRESQL

### Update .env
- `DATABASE_URL="postgresql://user:password@localhost:5432/your_database_name"`
- Replace user, password, and your_database_name with your actual database credentials.

### Create schema in `schema.prisma`


### Generate the Prisma client
- `npx prisma generate`

### Create and apply first migration
- `npx prisma migrate dev --name init`