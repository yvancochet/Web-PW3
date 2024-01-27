# Web-PW3 project
---
## Introduction

The aim of this project is to get familiar with modern developpment architecture with separated front-end and back-end.
The objective is to realise an app with a Node.js framework for the front-end and the back-end with a separate database.
We must expose an api via our back-end and use it with our front-end.

## Project

The project we decides to realise is a simple notes app. It is quite simlpe, one can create, edit, remove notes within a web interface that is fully responsive. <br/>
Here are the technology used : <br/>
<br/>

| **Part** | Technology   |
|---------- | --------|
| **back-end**  | Express |
| **front-end**  | React |
| **Linter**  | ESLint + Prettier |
| **ORM**  | Prisma |
| **DB**  | PostgresSQL |
| **Library manager**  | NPM / NPX |
| **main language**  | Typescript |
| **Communication with back-end**  | Fetch |

## Installation instruction
### Running app
To run the app, the only prequisit is to have docker desktop with docker compose installed. Also, ports 5432, 5000 and 3000 should be free to use. <br/>
Use the following command on root folder : <br/>
```
docker compose up --build
```
### App developpement
All of the instructions above were tester on a Windows Subsystem for linux and are aimed to be used on a linux system. <br/>
Since no dev container was used for this project, you must have the following installed on your machine, otherwise, you can create devcontainers yourself : <br/>
- NPM & NPX
- Node
- Docker Compose
<br/><br/>
The first step is to run the database in docker, from the root folder, execute the following command : <br/>
```
docker compose up -d db
```
Next step is to migrate database and run the backend. Go to the "notes-app-server" folder and run the following commands : <br/>
```
npx prisma db push
npm run start
```
Last step is to launch the front-end. Go to the "notes-app-ui" folder and type the following command : <br/>
```
npm run start
```

### Linter
To run linters, you can use eslint to find developpement errors and prettier to patch syntax errors using the following commands (from front-end or back-end folders) : <br/>
```
npx run eslint .
npx run prettier -w .
```

## front-end - back-end communication
Since the app is quite simple, there are only 4 requests that the front-end can do to the back-end :
- GET [get notes]
- POST [add note]
- PUT [edit note]
- DELETE [delete note]
<br/><br/>
These operations are done via browsing the back-end API, wwhich always returns data as json. The front-end then parses the data and display is properly to the user.<br/>
<img width="567" alt="image" src="https://github.com/yvancochet/Web-PW3/assets/71433754/0249eb25-73cb-44c8-a223-2e86dc041dad">
<br/><br/>

### Get note
<img width="827" alt="image" src="https://github.com/yvancochet/Web-PW3/assets/71433754/0f99b0ee-be3d-4d1e-b291-6cf2a1c84954">
<img width="766" alt="image" src="https://github.com/yvancochet/Web-PW3/assets/71433754/91c3cfcd-9681-41f3-a3a3-ece83d9a15fd">

### Add note
<img width="829" alt="image" src="https://github.com/yvancochet/Web-PW3/assets/71433754/c44b912c-231a-4359-8f23-23e6508149a9">
<img width="813" alt="image" src="https://github.com/yvancochet/Web-PW3/assets/71433754/0344af8e-a460-4d49-bd0e-ad09daa3d8fd">


### Edit note
<img width="469" alt="image" src="https://github.com/yvancochet/Web-PW3/assets/71433754/0e787d7b-c32e-49aa-b0b6-833f86f306c9">
<img width="396" alt="image" src="https://github.com/yvancochet/Web-PW3/assets/71433754/afadafc1-8e82-4880-8672-81cd884d606a">
<img width="777" alt="image" src="https://github.com/yvancochet/Web-PW3/assets/71433754/e5e7f2d4-40ec-4baa-a6e5-270a2915835b">


### Delete note
<img width="398" alt="image" src="https://github.com/yvancochet/Web-PW3/assets/71433754/6d505660-92c3-4335-95d5-a1ebdf4ee343">
<img width="707" alt="image" src="https://github.com/yvancochet/Web-PW3/assets/71433754/80de6511-bb13-49d7-9441-c98a74cb11db">
<img width="769" alt="image" src="https://github.com/yvancochet/Web-PW3/assets/71433754/017b9356-b06a-49ce-9bc2-5cea265be56f">




