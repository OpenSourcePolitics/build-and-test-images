#  Build and test images action

Allows to build and test Docker images.

Based on the [Build and push images action](https://github.com/OpenSourcePolitics/build-and-push-images-action)

## Inputs
- registry:
  - description: 'Registry url'
  - required: true
- namespace:
  - description: 'Registry namespace'
  - required: true
- password:
  - description: 'Password'
  - required: true
- username:
  - description: 'Username'
  - required: false
  - default: "userdoesnotmatter"
- image_name:
  - description: 'Image name'
  - required: true
- tag:
  - description: 'Image tags'
  - required: true
- database_username:
  - description: 'Database username'
  - required: true
- database_password:
  - description: 'Database password'
  - required: true
- database_host:
  - description: 'Database host'
  - required: true
- push:
  - description: 'Push image to registry'
  - required: true
  - default: "true"

## Usage

```yaml
- name: Build and test Docker image
  uses: OpenSourcePolitics/build-and-test-images-action@v1
  with:
    registry: ${{ secrets.REGISTRY_URL }}
    namespace: ${{ secrets.REGISTRY_NAMESPACE }}
    password: ${{ secrets.REGISTRY_PASSWORD }}
    username: ${{ secrets.REGISTRY_USERNAME }}
    image_name: ${{ secrets.REGISTRY_IMAGE_NAME }}
    tag: ${{ github.ref }}
    database_username: ${{ secrets.DATABASE_USERNAME }}
    database_password: ${{ secrets.DATABASE_PASSWORD }}
    database_host: ${{ secrets.DATABASE_HOST }}
    push: "true"
```

