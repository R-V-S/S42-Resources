If not using it with Rails, you can specify an alternate filepath/name for it by defining `Figaro.application.path` and then calling `Figaro.load`. For example, to use a file named `.env` in the parent directory when called from the 'spec' directory, you could include this at the top of your spec helper file (just below the requires):

```rb
Figaro.application.path = File.expand_path('../.env')
Figaro.load
```
