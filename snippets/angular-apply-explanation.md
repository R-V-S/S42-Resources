The `mousemove` event is triggered and functions properly, and `$scope.value` is updated as well – but Angular's automatic data-binding isn't triggered, so the DOM isn't updated to reflect the changes to `$scope.value`. 

This is because Angular tries to update the DOM only when necessary, and if Angular itself doesn't execute a change to the value of an Angular variable, then it doesn't know that it needs to update the DOM.

In a nutshell, `$apply` is needed whenever code is executed "out of turn", i.e. when there's a time-delay between when Angular's code runs and when the DOM is changed (i.e. if a callback function that's not part of the Angular ecosystem, like a jQuery event handler, is responsible for making the change).