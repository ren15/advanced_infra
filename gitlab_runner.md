

https://docs.gitlab.com/runner/register/

https://docs.gitlab.com/runner/install/docker.html



```bash
docker volume create gitlab-runner-config

docker run --rm -it -v gitlab-runner-config:/etc/gitlab-runner gitlab/gitlab-runner:latest register

docker run -d --name gitlab-runner --restart always \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v gitlab-runner-config:/etc/gitlab-runner \
    gitlab/gitlab-runner:latest

docker exec -it 

# concurrent = 5
# [runners.docker]
#   pull_policy = ["if-not-present"]

docker restart

```



## image from private registry

https://docs.gitlab.com/ee/ci/docker/using_docker_images.html

```bash
docker login registry.example.com:5000 --username my_username --password my_password



```
save `~/.docker/config.json` to CI/CD variable `DOCKER_AUTH_CONFIG`


