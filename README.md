# Http4s ScalaJS Example App

In order to run this locally

```
sbt
project backend
~reStart
```

# The bug in question
Was a problem that in development with `~reStart` all of the static files I was serving up had been found just fine. However, when attempting to package with `sbt-assembly`, they were not found and we got a bunch of NPE's as a result. The distinguishing features are:

- Static resources in a `/static` folder in the backend's resources
- Static file service mounted at `/static'
- A basepath on the static file service to add that root dir to the pathInfo

Run the app with `backend/reStart`. The cat should appear.

Run the app with `backend/run`. The cat should not appear.
