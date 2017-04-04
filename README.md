# Learn Angular 2 with Firebase

Simple way to start with angular 2 and firebase

## Install Node.JS

brew install node

## Install Typescript (Global)

sudo npm install typescript -g typescript

## Install Angular-CLI (Global)

sudo npm install -g @angular/cli

## Start a new project with Angular-CLI

ng new myproject

## Serve this new app

cd myproject
ng serve

## Create a new project in [Firebase](https://firebase.google.com/?hl=pt-br)

Change rules in Database >> Rules like this:

```json
{
  "rules": {
    ".read": "true",
    ".write": "true"
  }
}
```
