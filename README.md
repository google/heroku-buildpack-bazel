# heroku-buildpack-bazel
Heroku buildpack for bazel

## Procfile
Procfile should be:
```
bazel run //dir:binary_target
```
