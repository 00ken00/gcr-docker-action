## gcr-docker-action



## Example
```yaml
name: Build and push to GCR

on:
  push:
    branches:
      - 'releases/**'
  pull_request:
    branches: [ master ]

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
