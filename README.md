# Build a Serverless Web Application
### with AWS Lambda, Amazon API Gateway, AWS Amplify, Amazon DynamoDB, and Amazon Cognito

In this technical walkthrough, we will create a simple serverless web application that enables users to request car rides from the "Wild Rydes" (Uber-like) fleet. The application will present users with a pre-built HTML-based user interface for indicating the location where they would like to be picked up and will interact with a RESTful web service on the backend to submit the request and dispatch a nearby car ride. The application will also provide facilities for users to register with the service and log in before requesting rides.

### Prerequisites

To complete this tutorial, you will need an AWS account, AWS CLI installed in your local terminal, an account with [ArcGIS](https://www.arcgis.com/sharing/rest/oauth2/authorize?client_id=arcgisonline&response_type=token&display=default&state=%7B%22portalUrl%22%3A%22https%3A%2F%2Fwww.arcgis.com%22%2C%22useLandingPage%22%3Atrue%2C%22clientId%22%3A%22arcgisonline%22%7D&expiration=20160&locale=en-us&redirect_uri=https%3A%2F%2Fwww.arcgis.com%2Fhome%2Faccountswitcher-callback.html&force_login=true&hideCancel=true&showSignupOption=true&canHandleCrossOrgSignIn=true&signuptype=esri&redirectToUserOrgUrl=true&allow_verification=true) to add mapping to your app, a text editor, and a web browser.

### Application architecture

![Application Architecture](./images/architecture.jpg)

- Amplify Console provides continuous deployment and hosting of the static web resources including HTML, CSS, JavaScript, and image files which are loaded in the user's browser.
- JavaScript executed in the browser sends and receives data from a public backend API built using Lambda and API Gateway.
- Amazon Cognito provides user management and authentication functions to secure the backend API. 
- DynamoDB provides a persistence layer where data can be stored by the API's Lambda function.