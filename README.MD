# README - Orion HRMS Meeting App

This is the repository for the meeting app functionality of Orion HRMS. It uses the Amazon Chime SDK and Chime SDK UI Component Library to build a react meeting app.

## To run the app locally:

1. If you haven't already, [configure your AWS credentials](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html).

2. In the root directory, run `npm install`

3. Start the webpack server and node server concurrently: `npm start`

4. Open https://0.0.0.0:9000/ in your browser

## To deploy this as a serverless app

### Install aws and sam command line tools

- [Install the AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv1.html)
- [Install the AWS SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html)

### Run deployment script

The following will create a CloudFormation stack containing a Lambda and API Gateway deployment that will run the app. Note that S3 bucket name should be globally unique.

```
cd /serverless
node ./deploy.js -r us-east-1 -b <YOUR-S3-BUCKET-NAME> -s <YOUR-CLOUDFORMATION-STACK-NAME>
```

The script will create an S3 bucket and CloudFormation stack with Lambda and API Gateway resources required to run the meeting app. After the script finishes, it will output a URL that can be opened in a browser.
