

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

docker restart

```