# Learn Angular 4 with Firebase

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

## Add Firebase configs to your Angular 4 app

Go to Overview in Firebase Console and click the button "Add Firebase to your web app", u will see something like this:

```javascript
<script src="https://www.gstatic.com/firebasejs/3.7.4/firebase.js"></script>
<script>
  // Initialize Firebase
  var config = {
    apiKey: "HKJAShdjash-KAJSHdjahsjdHASDhj",
    authDomain: "yourapp.firebaseapp.com",
    databaseURL: "https://yourapp.firebaseio.com",
    projectId: "yourapp",
    storageBucket: "yourapp.appspot.com",
    messagingSenderId: "19827391827"
  };
  firebase.initializeApp(config);
</script>
```

Click the "COPY" button and paste it into your Angular App myproject/src/index.html like this:

```html
<body>

<script src="https://www.gstatic.com/firebasejs/3.7.4/firebase.js"></script>
<script>
  // Initialize Firebase
  var config = {
    apiKey: "HKJAShdjash-KAJSHdjahsjdHASDhj",
    authDomain: "yourapp.firebaseapp.com",
    databaseURL: "https://yourapp.firebaseio.com",
    projectId: "yourapp",
    storageBucket: "yourapp.appspot.com",
    messagingSenderId: "19827391827"
  };
  firebase.initializeApp(config);
</script>
</body>
```

## Testing if it's working

Go back to your Database in Firebase console and put a message as root node, just like this:

yourapp="Hello World from Firebase!"

Go back to Angular App src/index.html file and type this under Firebase configuration:

```javascript
var root = firebase.database().ref();

root.on('value', function(snap){
  console.log(snap.val());
});
```




