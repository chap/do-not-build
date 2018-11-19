# Do Not Build

The buildpack that prevents builds.

Helpful if you're trying to force your team to use pipeline promotions.

## Heroku Usage

Add to app
```
heroku buildpacks:add --index 1 chap/do-not-build -app app-name
```

Customize error message
```
heroku config:set DO_NOT_BUILD='This app should be deployed via pipeline promotion' -app app-name
```

Stop builds
```
git push heroku

-----> https://buildpack-registry.s3.amazonaws.com/buildpacks/chap/do-not-build.tgz app detected
!!!!!!
!!!!!! This app should be deployed via pipeline promotion
!!!!!!
 !     Push rejected, failed to compile
```

Remove buildpack to allow builds
```
heroku buildpacks:remove chap/do-not-build
```
