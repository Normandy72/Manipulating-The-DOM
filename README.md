## Manipulating the DOM with link
### Step 1: Declare Link Function
```
function MyDirective(){
    var ddo = {
        scope: {...},
        link: linkFunction,
        ...
        templateUrl: 'template.html'
    };
    return ddo;
}
```
### Step 2: Define the Link Function
```
function LinkFunction(scope, element, attrs, controller){
    ...
}
```