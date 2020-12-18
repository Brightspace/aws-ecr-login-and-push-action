# aws-ecr-login-and-push-action

Github action for logging into and pushing to an ECR repository.

## Usage

Push a local docker image identity by `source-image` to the `ecr-repository` with the tag `ecr-image-tag`.

```
  - name: docker push
    uses: Brightspace/aws-ecr-login-and-push-action@v0.0.0
    with:
        aws-account-id: 111111111111
        aws-region: us-east-1
        ecr-repository: d2l-hello-world
        ecr-image-tag: ${{ github.sha }}
        source-image: hello-world
```

This action assumes AWS credentials are already setup in the environment.  See [aws-actions/configure-aws-credentials](https://github.com/aws-actions/configure-aws-credentials) if you need to assume a role.