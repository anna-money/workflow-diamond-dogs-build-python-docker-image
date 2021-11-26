# Workflow to build Docker image

## Example

```yml
build-image:
  uses: anna-money/workflow-build-docker-image/.github/workflows/build-docker-image.yml@master
  with:
    name: "image-name"
    src_path: "path/to/src"
    version: "1.0.0"
    registry: "gcr.io/registry"
  secrets:
    gcloud_service_account_key: <key>
    pypi_user: <user>
    pypi_password: <password>
```
