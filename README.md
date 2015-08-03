more angular-tree-repeat examples
===================

Combined [ngDraggable](https://github.com/fatlinesofcode/ngDraggable) with [angular-tree-repeat](https://github.com/stackfull/angular-tree-repeat) for drag and drop functionality.

There is an example with a [horizontal tree here](https://rhildred.github.io/angular-tree-repeat).

There is an example with a [top down tree here](https://rhildred.github.io/angular-tree-repeat/topDown.html).

There is an example with a [more complicated top down tree with side panels here](https://rhildred.github.io/angular-tree-repeat/topDown.html).

About angular-tree-repeat
-----

Adds a pair of directives that can be used to display recursive (tree) data.

See http://blog.stackfull.com/2014/02/trees-in-angularjs/ for the back story.

angular-tree-repeat Usage
-----

The directives should be included in your page and the module `sf.treeRepeat`
included as a dependency:

    angular.module('myModule', ['sf.treeRepeat']);

Then use the directive `sf-treepeat` and `sf-treecurse` as follows:

    <ul>
      <li sf-treepeat="node in children of treeData">
        {{node.name}}
        <ul>
          <li sf-treecurse></li>
        </ul>
      </li>
    </ul>

About ngDraggable
-------

Adds directives for drag and drop.

ngDraggable Usage
----

- Add `angular` and `ngDraggable` to your code:

```html
<script src="//ajax.googleapis.com/ajax/libs/angularjs/1.3.8/angular.min.js"></script>
<script src="ngDraggable.js"></script>
```

- Add a dependency to the `ngDraggable` module in your application.

```js
angular.module('app', ['ngDraggable']);
```

- Add attribute directives to your html:


Draggable usage:
```html
<div ng-drag="true" ng-drag-data="{obj}" ng-drag-success="onDragComplete($data,$event)" ng-center-anchor="true">
  Draggable div
</div>
```

* `ng-center-anchor` is optional. If not specified, it defaults to false.
* If the draggable is also clickable (ng-click, ng-dblclick) the script wont react.
* You can define a drag-button as child with the attribute `ng-drag-handle`.

```ng-drag-start``` and ```ng-drag-move``` is also available. Add to the ng-drop element.
``ng-drag-stop`` can be used when you want to react to the user dragging an item and it wasn't dropped into the target container.

```draggable:start```, ```draggable:move``` and  ```draggable:end``` events are broadcast on drag actions.


Drop area usage:
```html
<div ng-drop="true" ng-drop-success="onDropComplete($data,$event)" >
  Drop area
</div>
```

### Angular Controller:

```js
app.controller('MainCtrl', function ($scope) {
    $scope.onDragComplete=function(data,evt){
       console.log("drag success, data:", data);
    }
    $scope.onDropComplete=function(data,evt){
        console.log("drop success, data:", data);
    }
 };
```
