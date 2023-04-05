# AWS Frontend Web App Deploy Stack

This is an AWS CDK Construct to make deploying a Frontend Web App (SPA) deploy to S3 behind CloudFront.

## Install

### TypeScript

```shell
npm install @yicr/aws-frontend-web-app-deploy-stack
```
or
```shell
yarn add @yicr/aws-frontend-web-app-deploy-stack
```

## Example

```shell
npm install @yicr/aws-frontend-web-app-deploy-stack
```

```typescript
import { FrontendWebAppDeployStack } from '@yicr/aws-frontend-web-app-deploy-stack';

new FrontendWebAppDeployStack(app, 'FrontendWebAppDeployStack', {
  env: { account: '012345678901', region: 'us-east-1' },
  domainName: 'example.com',
  hostedZoneId: 'Z0000000000000000000Q',
  originBucketName: 'frontend-web-app-example-origin-bucket', // new create in this stack
  deploySourceAssetPath: 'website/',
  logBucketArn: 'arn:aws:s3:::frontend-web-app-example-access-log-bucket', // already created
});

```