Rails 5 now converts params to an object when it gets passed from one view to another. It then requires you to convert it back to a hash if you want to access the values using the `.to_h` method... but there's a sort of security check that's involved with that conversion. You can either:

1. Explicitly permit certain values when converting back to a hash:

  ```ruby
params[:user].permit([:name, :password, :password_confirmation]).to_h
```

  That would give you a usable `user` hash to work with in your controller. (You'd have to remove `[:user]` from the lines in your `create` class, since you'd be passing `user` directly)

2. Since you're passing the entire user object anyway, you can bypass the "permit" process by using `.to_unsafe_h`. This line would fix your code without any other changes: 

  ```ruby
<%= button_to "Yes", {:controller => 'users', :action => 'create', :params => params.to_unsafe_h}, class: "btn btn-success" %>
```
It would basically emulate the Rails 4 behavior.