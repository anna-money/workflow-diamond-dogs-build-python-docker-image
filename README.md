# Workflow to build Docker image

This workflow allows you to build Docker image and puth it to Google Cloud Registry (GCR).

## Inputs

1. `name` - image name (string)
2. `version` - image version (string, required)
3. `registry` - Google Cloud Registry (string, required). Ex.: `eu.gcr.io/my-registry` 
4. `tag_latest` - tag this version as `latest` (boolean, default: `false`)
5. `src_path` - path to the source directory with `__init__.py` file to update `__version__` variable in it (string, default:  `''`)

## Outputs

1. `image` - full image name with registry and version. Ex.: `eu.gcr.io/my-registry/my-app:1.2.3`

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
