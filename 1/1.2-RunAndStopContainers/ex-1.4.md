# EXERCISE 1.4: MISSING DEPENDENCIES

Start a Ubuntu image with the process `sh -c 'while true; do echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website; done'`

You will notice that a few things required for proper execution are missing. Be sure to remind yourself which flags to use so that the container actually waits for input.

**_Note also that curl is NOT installed in the container yet. You will have to install it from inside of the container._**

Test inputting `helsinki.fi` into the application. It should respond with something like

```html
<html>
  <head>
    <title>301 Moved Permanently</title>
  </head>

  <body>
    <h1>Moved Permanently</h1>
    <p>The document has moved <a href="http://www.helsinki.fi/">here</a>.</p>
  </body>
</html>
```

This time return the command you used to start process and the command(s) you used to fix the ensuing problems.

Hint for installing the missing dependencies you could start a new process with `docker exec`.

This exercise has multiple solutions, if the curl for helsinki.fi works then it's done. Can you figure out other (smart) solutions?

## Answer:

1. **Start the process:**

```bash
docker run -it ubuntu sh -c 'while true; do echo "Input website:"; read website echo "Searching.."; sleep 1; curl http://$website; done'
```

2. **Fix the issue:**

```bash
# From another terminal
docker exec -it <container name / container id> bash

# Inside the container
apt-get update && apt-get install -y curl
```