# Angular JS

## Project Start Tips

 - ### Promises 
 Use [bluebird][bluebird], not `$q`
 ```JS
 function trackDigests(app) {
    app.run(["$rootScope",function ($rootScope) {
        Promise.setScheduler(function (cb) {
            $rootScope.$evalAsync(cb);
        });
    }]);
}


var app = angular.module('HelloApp', []);
trackDigests(app);
```

- If using `$timeout`, use a wrapper service instead that ensures your `$timeout` is cleared on `$destroy`
```JS
angular.module('safeTimeout', [])
.service('safeTimeout', function($timeout) {
  return function setTimeout(scope, fn, delay) {
      var promise = $timeout(fn, delay);
      var deregister = scope.$on('$destroy', function() {
          $timeout.cancel(promise);
      });
      promise.then(deregister);
  }
});

// Usage
update();
function update() {
    // do the actual updating here
    safeTimeout($scope, update, 30000);
}
```


[bluebird]: https://github.com/petkaantonov/bluebird
