# EXERCISE 1.3: SECRET MESSAGE

Now that we've warmed up it's time to get inside a container while it's running!

Image `devopsdockeruh/simple-web-service:ubuntu` will start a container that outputs logs into a file. Go inside the running container and use `tail -f ./text.log` to follow the logs. Every 10 seconds the clock will send you a "secret message".

Submit the secret message and command(s) given as your answer.

## Answer:

1. **Secret message**: 'You can find the source code here: https://github.com/docker-hy'

2. **Steps:**

```bash
docker run -d devopsdockeruh/simple-web-service:ubuntu

# use the returned container id 
# or check the container name with 'docker ps'

docker exec -it <container name/ container id> bash

# Execute inside the container
tail -f ./text.log
```
