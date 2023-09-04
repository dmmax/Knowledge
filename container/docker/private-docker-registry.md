# Private Docker Registry

## Push image
```shell
docker tag {image_id} {registry_host}:{registry_port}/{image_name}:{image_tag}
docker push {registry_host}:{registry_port}/{image_name}:{image_tag}
```

## Pull image
```shell
docker pull {registry_host}:{registry_port}/{image_name}:{image_tag}
```

## Links
* [Documentation: docker tag](https://docs.docker.com/engine/reference/commandline/tag/)