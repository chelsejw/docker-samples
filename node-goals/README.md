# Simple Express App

An express app for a simple goals app, where users can modify their goal.

## 1. Build the image
````
docker build . -t node-goals
````

## 2. Run a container from the image we built 

````
docker run -p 3000:80 -d --rm  --name node-goals-app node-goals
````

- `docker run` creates and starts the container with the CMD found in Dockerfile (in this case, it's `node server.js`)
- `-p 3000:80` _publishes_ a port on our computer (3000), and maps (not sure if this is the right word) it to the port 80 of the container. This is necessary because containers are isolated environments – we can't access the app running on the container's port 80 otherwise. 
- `-d` (optional) runs the container in _detached mode_. Without it, your terminal will be blocked while the container is running.
- `--rm` will _remove_ the container when it stops running
- `--name node-goals-app` (optional) _names_ the container.
- `node-goals` is the name of the image the container is being run from


## 3. Checkout the app on your http://localhost:3000


## 4. When you're done, stop the container.
````
docker stop node-goals-app
````

Note: if you did not name the container when you did `docker run` in step 2, you will need to run `docker ps` to find that container and replace `node-goals-app` with the container id from there.  