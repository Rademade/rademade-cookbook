Angular conventions
===================
### Modules
#### 1. Use angular.module('app').
#### 2. Avoid tight coupling and minimize dependencies.
#### 3. Refer to [reference](https://github.com/johnpapa/angular-styleguide#modules) for additional details.
### Controllers
#### 1. Write new controllers using class injection syntax:
- See [Example](https://github.com/Rademade/taiga-front/blob/master/app/modules/components/project-menu/project-menu.controller.coffee).

- Clarification: Angular dependency injection is handled by the class attribute

#### 2. Use controllerAs syntax:
- In ui-router routes:

    ```coffeescript
    .state 'dashboard',
      url: '/dashboard'
      templateUrl: 'app/dashboard/dashboard.jade'
      controller: 'DashboardController'
      controllerAs: 'dashboardCtrl'
    });
    ```

- In templates:

    ```html
    <div ng-controller="DashboardController as dashboardCtrl">
        {{ dashboardCtrl.user }}
    </div>
    ```

### Directives
#### 1. Use directives with parameters for reusable ui-components and template partials.
#### 2. Restrict DOM manipulation to directives.
#### 3. Use Events only in services or directives.
#### 4. Use module file structure for directives:

```javascript
app/
    directives/
        scroll/
            scroll.controller.coffee
            scroll.template.jade
            scroll.directive.coffee
```
