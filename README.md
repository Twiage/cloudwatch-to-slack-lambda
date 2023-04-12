# lambda-cloudwatch-slack

An [AWS Lambda](http://aws.amazon.com/lambda/) function for better Slack notifications. 
[Original blogpost about lambda setup](https://assertible.com/blog/npm-package-lambda-cloudwatch-slack)

## Overview

This function was originally derived from the
[AWS blueprint named `cloudwatch-alarm-to-slack`](https://aws.amazon.com/blogs/aws/new-slack-integration-blueprints-for-aws-lambda/). The
function in this repo improves on the default blueprint in several
ways:

**Better default formatting for CloudWatch notifications:**

![AWS Cloud Notification for Slack](https://github.com/assertible/lambda-cloudwatch-slack/raw/master/images/cloudwatch.png)

**Support for notifications from Elastic Beanstalk:**

![Elastic Beanstalk Slack Notifications](https://github.com/assertible/lambda-cloudwatch-slack/raw/master/images/elastic-beanstalk.png)

**Support for notifications from Code Deploy:**

![AWS CodeDeploy Notifications](https://github.com/assertible/lambda-cloudwatch-slack/raw/master/images/code-deploy.png)

**Basic support for notifications from ElastiCache:**

![AWS ElastiCache Notifications](https://github.com/assertible/lambda-cloudwatch-slack/raw/master/images/elasticache.png)

**Support for encrypted and unencrypted Slack webhook url:**


## Configuration

### 1. Clone this repository

### 2. Configure environment variables

```
cp .env.example .env
```

Fill in the variables in the `.env`. 

### 3. Setup Slack hook

Follow these steps to configure the webhook in Slack:

  1. Navigate to
     [https://slack.com/services/new](https://slack.com/services/new)
     and search for and select "Incoming WebHooks".

  3. Choose the default channel where messages will be sent and click
     "Add Incoming WebHooks Integration".

  4. Copy the webhook URL from the setup instructions and use it in
     the next section.

  5. Click 'Save Settings' at the bottom of the Slack integration
     page.


### 4. Deploy to AWS Lambda

The final step is to deploy the integration to AWS Lambda:

    npm install
    npm run deploy

## Tests

With the variables filled in, you can test the function:

```
npm install
npm test
```

## License

MIT License
