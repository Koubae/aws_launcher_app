AWS Launcher app
================

Sample project from the tutorial at --> **[Deploy a Web App on AWS Elastic Beanstalk](https://aws.amazon.com/getting-started/guides/deploy-webapp-elb/)**

The tutorial shows how to **deploy a non-containerized application in the cloud**.
The app is a NodeJS app but is just used as an example, what is really important is the 
**aws_cdk_launcher**


Documentation
-------------

* [AWS Elastic Beanstalk Documentation](https://docs.aws.amazon.com/elastic-beanstalk/?id=docs_gateway/?intClick=gsrc-2021)
* [Amazon Simple Storage Service (S3)](https://aws.amazon.com/s3/)
* [Get Started with AWS CDK](https://aws.amazon.com/getting-started/guides/setup-cdk/)
* [Configuration options for Elastic Beanstalk](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/command-options-general.html#command-options-general-autoscalingasg)
* [AWS CLI and get a list of all the supported plaftorms.](https://docs.aws.amazon.com/cli/latest/reference/elasticbeanstalk/list-available-solution-stacks.html)
* [Handling NodeJS dependencies in Elastic Beanstalk packages](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/nodejs-platform-dependencies.html)


* [Find the hands-on tutorials for your AWS needs](https://aws.amazon.com/getting-started/hands-on/?intClick=gsrc-2021&getting-started-all.sort-by=item.additionalFields.sortOrder&getting-started-all.sort-order=asc&awsf.getting-started-category=*all&awsf.getting-started-level=*all&awsf.getting-started-content-type=*all)

Commands
--------

```bash 
npm install -g cdk # Make sure that you have the latest CDK version.

mkdir aws_cdk_launcher
cd aws_cdk_launcher

# init cdk app 
cdk init app --language typescript


# node
#  aws-s3-assets
npm i @aws-cdk/aws-s3-assets
# Elastic Beanstalk CDK dependencies
npm i @aws-cdk/aws-elasticbeanstalk
# instance profile
npm i @aws-cdk/aws-iam



# Package the app inside the aws_cdk_launcher
zip -r ../app.zip ./*
# unzip (inside web app dir in case is not unzipped) 
zip -r app.zip .


# bootstrap app 
cdk bootstrap aws://ACCOUNT-NUMBER-1/REGION-1


# build and deploy cdk app
node run build
cdk deploy
# clean up aws env 
cdk destroy
```