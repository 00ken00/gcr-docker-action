## gcr-docker-action

Build and push image to GCR with tag: `latest,<branch_name>`


## Example
```yaml
name: Build and push to GCR

on:
  pull_request:
    branches: [ main ]
  push:
    branches:
      - 'releases/**'

jobs:
  build-and-push-to-gcr:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Build and push to GCR
        uses: KenExplore/gcr-docker-action@v2
        with:
          gcloud_service_key: ${{ secrets.GCR_CREDENTIALS }}
          registry: gcr.io
          project_id: <project-id>
          image_name: <image-name>
          dockerfile: ./Dockerfile
          context: .
```
