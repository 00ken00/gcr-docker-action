### Example

```yaml
name: Build and push to GCR

on:
  push:
    branches: [ master ]

jobs:
  build-and-push-to-gcr:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Build and push to GCR
        uses: KenExplore/gcr-docker-actions@v1
        with:
          - 
        

```
