# Full Stack Project

```ShellScript
# create the main project

mkdir fullstack_project
cd    fullstack_project

git init
npm init
npm install concurrently
echo node_modules/ > .gitignore

# create backend

mkdir backend
cd    backend

git init
npm init
npm install express mongoose
npm install --saveDev nodemon
echo node_modules/ > .gitignore
# create index.js file

# create frontend

create-react-app frontend
cd    frontend

git init
```

## Create Fullstack package.json

```JavaScript
{
  // ...
  "scripts": {
    // ...
    "setup": "git submodule init && git submodule update && npm install && npm --prefix frontend install && npm --prefix backend  install",
    "devel": " concurrently 'npm --prefix backend run devel' 'npm --prefix frontend run start' "
  },
  // ...
}
```

## Create Backend package.json

```JavaScript
{
  // ...
  "scripts": {
    // ...
    "start": "node index.js",
    "devel": "nodemon index.js"
  },
  // ...
}
```

## Create Frontend package.json

```JavaScript
{
  // ...
  "proxy": "http://localhost:5000/",
  // ...
}
```

## Create 3 Github Repos...

...for frontened backend and fulltack, then commit and push frontend and backend.

```ShellScript
git submodule init
git submodule add <frontend repo url> frontend
git submodule add <backend repo url> backend
git add .
git commit -m initialze
git add remote ... (from github)
git push ... (from github)
```

## Cloning the Project

```ShellScript
git clone ...

git submodule init
git submodule update
npm install
npm --prefix frontend install
npm --prefix backend  install

# OR
npm run setup
```