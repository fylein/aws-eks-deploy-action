<h3 align="center">AWS EKS Deployment Action</h3>
<p align="center">AWS EKS deployment for clusters running behind a VPC.<p>


## Setup

This GitHub Action requires a bunch of environment variables, check the env section below.
  
```yaml
# .github/workflows/deploy.yml 
name: Continuous Deployment

on:
  push:
    branches:
      - master

jobs:
  assign:
    name: Deploy to Production
    runs-on: ubuntu-latest
    steps:
    - name: deploy to production
      uses: fylein/aws-eks-deploy-action@master
      env:
        EKS_CLUSTER_NAME: ${{ secrets.EKS_CLUSTER_NAME }}
        AWS_REGION: ${{ secrets.AWS_REGION }}
        LOCAL_HOST: ${{ secrets.LOCAL_HOST }}
        LOCAL_PORT: ${{ secrets.LOCAL_PORT }}
        REMOTE_PORT: ${{ secrets.REMOTE_PORT }}
        EKS_KUBECTL_ROLE: ${{ secrets.EKS_KUBECTL_ROLE }}
        ROLE_SESSION_NAME: ${{ secrets.ROLE_SESSION_NAME }}
        AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
        AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
        DOCKERHUB_USERNAME: ${{ secrets.DOCKERHUB_USERNAME }}

```
