Password reset with Angular2-Token and Devise Token Auth involves some back-and-forth interplay. The workflow goes something like this:

The goal is a UI that follows this workflow for the user:

Password reset form -> email -> password update form -> success!

To accomplish that, all you need are new 2 Angular components (password reset and password update) and some configuration changes.

Step by step:

1. Configure Angular2-Token's `resetPasswordCallback` setting to point to a path that will hold the "update password" component. It wants an absolute URL, so something like this should do the trick:

  ```js
this._tokenService.init({
  resetPasswordCallback: `${window.location.protocol}//${window.location.host}/#/update_password`
});
```

2. Create a "reset password" component  & route. There's a `ResetPasswordData` object, just as there is a `RegisterData` and `SignInData` object provided by Angular2-Token.

  The form only needs an email address. 

  On submit, call [Angular2-Token's .resetPassword() method](https://github.com/neroniaky/angular2-token#resetpassword) and pass it the email address. 

  That will send a POST request to Devise Token Auth's route for `/password`. Devise Token Auth will then generate a reset password token and email the user with a link to Devise Token Auth's route for `/password/edit` – which, in turn, will redirect the user to Angular2-Token's `resetPasswordCallback` path, where the user can update their password. 

3. Create the "update password" component & route. There's an `UpdatePasswordData` object that you can use.

