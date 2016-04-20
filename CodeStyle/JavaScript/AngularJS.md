Angular conventions
===================
### Modules
1. Use angular.module('app').
2. Avoid tight coupling and minimize dependencies.
3. Refer to [reference](https://github.com/johnpapa/angular-styleguide#modules) for additional details.

### Controllers
1. Write new controllers using class injection syntax:
- See [Example](https://github.com/Rademade/taiga-front/blob/master/app/modules/components/project-menu/project-menu.controller.coffee).
- Clarification: Angular dependency injection is handled by the class attribute

#### 2. Use controllerAs syntax:
Router definition:

```coffeescript
  .state 'dashboard',
  	url: '/dashboard'
  	templateUrl: 'app/dashboard/dashboard.jade'
  	controller: 'DashboardController'
  	controllerAs: 'dashboardCtrl'
  });
```

Templates:

```html
	<div ng-controller="DashboardController as dashboardCtrl">
		{{ dashboardCtrl.user }}
	</div>
```

### Directives
1. Use directives with parameters for reusable ui-components
2. Use directives for template partials
2. Restrict DOM manipulation to directives
3. Use Events only in services or directives
4. Correct directive naming with dash – `directive-name`  
5. Use module file structure for directives

```javascript
app/
    directives/
        scroll-top/
            controller.coffee
            template.jade
            directive.coffee
```
