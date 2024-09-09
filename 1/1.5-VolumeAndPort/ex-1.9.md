# EXERCISE 1.9: VOLUMES

In this exercise we won't create a new Dockerfile.

Image `devopsdockeruh/simple-web-service` creates a timestamp every two seconds to `/usr/src/app/text.log` when it's not given a command. Start the container with a bind mount so that the logs are created into your filesystem.

Submit the command you used to complete the exercise.

**Hint:** read the note that was made just before this exercise!

## Answer 

```bash
touch logs.txt

docker run -v "$(pwd)/logs.txt:/usr/src/app/text.log" devopsdockeruh/simple-web-service
```