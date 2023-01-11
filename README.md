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
***
##### _Summary_
* DOM manipulation usually done inside of the link function declared on the DDO.
* Link function does not support injection. To use injected components, services, inject them into directive.
* 'scope' parameter is the exact `$scope` in directive's controller.
* 'element' object represents the element of the directive:
    * Top level element.
    * It's jqLite object or jQuery object (if jQuery is included before Angular).
***