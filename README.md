# Installation
1. Pull the repository locally.
2. Configure AWS CLI sso session, profile (sandbox), default region.
3. `npm install`
4. `npx cdk deploy --profile sandbox`

# Engineering Log from the Typescript workshop
https://cdkworkshop.com/20-typescript.html

### Create a sandbox environment
- See sandbox tutorial on onboarding document.

### Create project directory and initialize a CDK app:
`mkdir cdk-workshop && cd cdk-workshop`

`cdk init sample-app --language typescript`

### Synthesize a template from your app
`cdk synth`

### Bootstrap the environment
`cdk bootstrap --profile sandbox`

### Deploy the app
`cdk deploy --profile sandbox`

> Q: why did this deploy the app to AWS Region us-east-1? 
> A: because the CLI's default region is us-east-1 and our control tower is in us-east-2. 

### Destroy and deploy the app to us-east-2 

for the sake of playing around and in order to keep all our resources in the same region as our control tower (easier to audit via the console)

`cdk destroy --profile sandbox`

`export AWS_DEFAULT_REGION=us-east-2`

`cdk bootstrap --profile sandbox`

`cdk deploy --profile sandbox`

## Useful commands

* `npm run build`   compile typescript to js
* `npm run watch`   watch for changes and compile
* `npm run test`    perform the jest unit tests
* `cdk deploy`      deploy this stack to your default AWS account/region
* `cdk diff`        compare deployed stack with current state
* `cdk synth`       emits the synthesized CloudFormation template
