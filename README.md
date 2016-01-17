# Angular Dynamic Controller

This directive allows you to dynamically specify a controller name to inject into html template 

## Installation

Install using `bower`

    bower install --save angular-dynamic-controller

Load the script files into your application.

```html
<script src="bower_components/angular/angular.js"></script>
<script src="bower_components/angular-dynamic-controller/lib/angular-dynamic-controller.js"></script>
```

Add this module as a dependency in your AngularJS app.

```javascript
angular.module('myApp', [ 'aj.angular-dynamic-controller' ]);
```

## Usage

The `dynamicController` directive which include the controller name dynamically.

To use this directive use attribute 'dynamic-controller' in the following way.

```html
<tabset> 
	<tab ng-repeat="tab in tabs" active=tab.active> 
		<tab-heading>{{tab.title}} </tab-heading>
			<div ng-include="tab.template" dynamic-controller="tab.controller"></div>
	</tab> 
</tabset>
```

```javascript
var myApp = angular.module('myApp',[]);

myApp.controller('TabCtrl', ['$scope', function($scope) {
  
  $scope.tabs = [{
  		tab.template="main.html",
  		tab.controller="MainCtrl"
	}];

}]);
```
