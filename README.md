# heroku-buildpack-bazel
Heroku buildpack for [Bazel](http://www.bazel.io). Currenly, only Java is supported.

Bazel is an open-source build tool created by and for the engineers at Google.

## Required files
1. `BUILD`
  See the documentation on top-level [BUILD](http://www.bazel.io/docs/tutorial/java.html#creating-your-own-build-file) files.
2. `WORKSPACE`
  See the documentation on [Bazel WORKSPACE](http://www.bazel.io/docs/tutorial/workspace.html).
3. `build_path`
   This file should contain text for the bazel path to the deploy jar for your application.
   For example, if the path to your `java_binary` target is `pkg:server`, this file should contain:
   ```text
   pkg:server_deploy.jar
   ```

## Default Procfile
The default `Procfile` is:
```Procfile
web: .jdk/bin/java -jar app.jar
```

This does not need to be included in your app.

If you need custom JVM flags, you'll need to include a custom `Procfile` with your application. Modify the line above with the flags you want.

## Use this buildpack
```shell
heroku buildpacks:set https://github.com/google/heroku-buildpack-bazel
```
