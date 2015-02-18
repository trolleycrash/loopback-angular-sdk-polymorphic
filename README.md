#loopback-angular-sdk-polymorphic-issue

A repository for reproducing an issue with loopback-angular-sdk, in which lb-ng is ignorant of polymorphic relations.

For more details see: https://github.com/strongloop/loopback-sdk-angular-cli/issues/16#issuecomment-74871369

###To reproduce

1. clone the repo
2. `npm install`
3. `lb-ng server/server.js client/lb-services.js`

###Result
```
Loading LoopBack app "/home/tleigh/workspace_extraordinator/loopback-angular-sdk-polymorphic/server/server.js"
Generating "lbServices" for the API endpoint "/api"
Warning: scope User.accessTokens targets class "AccessToken", which is not exposed 
via remoting. The Angular code for this scope won't be generated.
Warning: scope Picture.imageable is missing _targetClass property.
The Angular code for this scope won't be generated.
Please upgrade to the latest version of
loopback-datasource-juggler to fix the problem.
Saving the generated services source to "/home/tleigh/workspace_extraordinator/loopback-angular-sdk-polymorphic/client/lb-services.js"
```

In addition, `lb-services.js` contains no references to `Author.image()` nor `Reader.image()` as one would expect.









