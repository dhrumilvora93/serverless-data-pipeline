# A Serverless data pipeline

Using AWS Cloud Services Lambda, S3, Glue and Athena we are going to build a data pipeline written in python and deploy it using the Serverless Framework.

# Deploy and run the data pipeline

make sure you have correct user and roles defined:

### Create a user to access AWS

create an user with Programmatic access using the AWS console and set the credentials under a [serverless] section in the credentials file located in 

   ~/.aws/credentials

### Create the necessary roles

for our project we need two roles; 

* one for lambda - AWS Lambda Full ACCESS policy, AWS Glue Service Role
* one for glue. - AWS Glue Service Role, S3 FULL ACCESS

create roles and for both these roles and keep the ARN somewhere accessible.

Replace the ARN of the lambda role and the ARN of the Glue role with the ones defined in the serverless.yml file. There is a comment above both roles that indicates that you should replace the ARN.

### configure your local environment

git clone https://github.com/dhrumilvora93/serverless-data-pipeline.git

- cd serverless_data_pipeline_example

under the root of this project execute:

1. export AWS_PROFILE="serverless"
2. pip install awscli
3. sudo npm install -g serverless
4. npm install serverless-s3-remover

to deploy the data pipeline execute:

# replace the `unique-identifier` with something unique
sls deploy --stage unique-identifier
to remove the data pipeline execute:

# replace the `unique-identifier` with something unique
sls remove --stage unique-identifier

Referred the article to build the pipline: https://medium.com/@vincentclaes_43752/build-a-serverless-data-pipeline-on-aws-7c7d498d9707

Thanks @vincentclaes for this greate tutorial. You could follow him at https://github.com/vincentclaes