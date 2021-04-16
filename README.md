## Introduction

This repo contains reproduction for https://github.com/prisma/prisma/issues/6594


This reproduction was done on windows but it is also reproducible on Linux. Please remove `.exe` and other implied things if you trying this on other OS. 

## Steps

0. Clone the repo and run `yarn`
1. Get a query-engine binary on the root of the folder. This reproduction contains a windows binary but you should get one for your platform. You can get one from `node_modules/@prisma/engines` after you comment the binary path in `.env` temporarily and run `prisma version`. That will force a binary download and you can use that for reproduction. 
2. Make sure the `PRISMA_QUERY_ENGINE_BINARY` is pointing to the binary you just placed in the root relatively. The example that I have is `./query-engine.exe`
3. Run `prisma version` to check if the cli is picking up the binary
4. Run `yarn start` to reproduce. The program will throw ENOENT while reading the binary.
