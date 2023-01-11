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
## Using Directive’s transclude to Wrap Other Elements
### Step 1: Set transclude to true
```
function MyDirective(){
    var ddo = {
        scope: {...},
        transclude: true,
        ...
        templateUrl: "template.html"
    };
    return ddo;
}
```
### Step 2: Wrap Some Parent Content
```
<my-directive>
    <span>
        WARNING! WARNING! {{ctrl.someProp}}
    </span>
</my-directive>
```
`{{ctrl.someProp}}` - evaluated in the parent controller, NOT in our directive

### Step 3: ng-transclude To Place Wrapper Content
```
<div>
    ...
    <div ng-transclude></div>
</div>
```
`<div ng-transclude></div>` - insert evaluated wrapped content into element marked with ng-transclude

***
##### _Summary_
* `transclude` allows whole templates to be passed into a directive.
* The wrapped content is evaluated in the parent's context, NOT in the directive's context.
* In the DDO:
    * transclude: true
* In directive's template:
    * ng-transclude attribute designates place for evaluated wrapped content.
***