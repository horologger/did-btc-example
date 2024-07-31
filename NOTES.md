nvm use v20.11.1
git init
npm init -y
mkdir src
npm install -D typescript @types/node
npx tsc --init

// Replace tsconfig.json contents with
{
  "compilerOptions": {
     "target": "es2016",
     "module": "commonjs",
     "rootDir": "./",
     "resolveJsonModule": true, /* in case you are importing JSON files */
     "outDir": "./dist",
     "esModuleInterop": true,
     "forceConsistentCasingInFileNames": true,
     "strict": true,
     "noImplicitAny": true,
     "skipLibCheck": true,
     "sourceMap": true
  }
}

src/index.ts

import http from "http";
export const server = http.createServer((req, res) => {
  res.writeHead(200, { "Content-Type": "application/json" });
  res.end(
    JSON.stringify({
      data: "It Works!",
    })
  );
});
server.listen(3000, () => {
  console.log("Server running on http://localhost:3000/");
});

npm run local:watch

