# Do Not Build

The buildpack that prevents builds.

Helpful if you're trying to force your team to use pipeline promotions.

# Heroku Usage

Add to app
```
heroku buildpacks:add --index chap/do-not-build -app app-name
```

Customize error message
```
heroku config:set DO_NOT_BUILD='This application should be deployed via pipeline promotion' -app app-name
```

Stop builds
```
git push heroku

-----> https://github.com/chap/do-not-build app detected
!!!!!!
!!!!!! This application should be deployed via pipeline promotion
!!!!!!
 !     Push rejected, failed to compile https://github.com/chap/do-not-build app.
 !     Push failed
```
