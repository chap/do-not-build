# Do Not Build

The buildpack that prevents builds.

Helpful if you're trying to force your team to use pipeline promotions.

## Heroku Usage

Add to app
```
heroku buildpacks:add --index 1 chap/do-not-build
```

Customize error message
```
heroku config:set DO_NOT_BUILD='This app should be deployed via pipeline promotion'
```

Stop builds
```
git push heroku

-----> chap/do-not-build app detected
!!!!!!
!!!!!! This app should be deployed via pipeline promotion
!!!!!!
 !     Push rejected, failed to compile
```

Remove buildpack to allow builds
```
heroku buildpacks:remove chap/do-not-build
```
