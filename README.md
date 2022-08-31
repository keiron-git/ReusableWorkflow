<p align="center">
  <img src="https://avatars0.githubusercontent.com/u/44036562?s=100&v=4"/> 
</p>

## Templates repository

In this repository are the actions for the deployment

#### Utils:

- [Github Action Docs](https://docs.github.com/es/actions)

#### Example (buildKanikoAndChangeImage):

```
name: NAME
on:
  workflow_dispatch:
  push:
    branches:
      - "develop"
jobs:
  deployment:
    uses: keiron-git/ReusableWorkflow/.github/workflows/buildKanikoAndChangeImage.yml@main
    with:
      namespace: NAMESPACES
      app_name: APPNAME
      image_repository_name: NAME_ECR
      cluster_name: EKS_NAME
      environment: ENVIRONMENT
      runner: RUNNER
    secrets:
      aws_account_id: ${{ secrets.AWS_ACCOUNT_ID }}
      personal_token: ${{ secrets.PERSONAL_TOKEN }}
```

#### Example (buildImageAndPublishECR):

```
name: NAME
on:
  workflow_dispatch:
  push:
    branches:
      - "develop"
jobs:
  deployment:
    uses: keiron-git/ReusableWorkflow/.github/workflows/buildImageAndPublishECR.yml@main
    with:
      namespace: NAMESPACES
      app_name: APPNAME
      image_repository_name: NAME_ECR
      cluster_name: EKS_NAME
      environment: ENVIRONMENT
      runner: RUNNER
    secrets:
      aws_account_id: ${{ secrets.AWS_ACCOUNT_ID }}
      personal_token: ${{ secrets.PERSONAL_TOKEN }}
```
