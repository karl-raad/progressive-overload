Progressive Overload is a demo app designed with Angular 18 and AWS serverless architecture.
This is a fitness app that allows to keep an exercises history, view progress charts and motivates to beat personal bests.
The infrastructure is deployed using AWS CDK nodeJS 20.

The front end leverages Angular 18's features such as standalone componenents, typed forms, component lazy loading, RxJS, advanced dependency injection, Signals API...
It is packaged by feature, uses responsive design to support mobile devices and uses Material UI with light and dark themes
It is hosted on a public AWS S3 bucket.

The back end leverages AWS Access Gateway, Lambda, DynamoDB and Cognito.
It uses indexes of DynamoDB to optimize queries over scans.
Cognito handles authentication with email verification and a custom welcom email.

To deploy the front end:
- git clone the progressive-overload-frontend repository
- cd to progressive-overload-frontend
- npm install
- ng serve to test
  OR if you have an AWS account
- npm build --configuration production
- cd to /cdk folder
- cdk bootstrap
- cdk deploy (to host on an aws s3 bucket)

To deploy the back end (includes dev stack and prod stack):
- git clone the progressive-overload-backend repository
- cd to progressive-overload-backend
- npm run bundle (uses esbuild to bundle lambda functions)
- cdk bootstrap
- cdk deploy --context stage=dev
  And / OR
- cdk deploy --context stage=prod

