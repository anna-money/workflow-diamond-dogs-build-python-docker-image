# Workflow to build Docker image

This workflow allows you to build Docker image and push it to Google Cloud Registry (GCR).

## Inputs

1. `name`  (string, required) - image name
2. `version` (string, required) - image version
3. `registry` (string, required) - Google Cloud Registry. Ex.: `eu.gcr.io/my-registry`
4. `tag_latest` (boolean, default: `false`) - tag this version as `latest`
5. `src_path` (string, default:  `''`) - path to the source directory with `__init__.py` file to update `__version__`
   variable in it. Ignored by default.

## Secrets

1. `gcloud_service_account_key` - Key to access to Google Cloud Registry
2. `pypi_user` - PyPI user
3. `pypi_password` - PyPI password

## Outputs

1. `image` (string) - full image name with registry and version. Ex.: `eu.gcr.io/my-registry/my-app:1.2.3`

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
