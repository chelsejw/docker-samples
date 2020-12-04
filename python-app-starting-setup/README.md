# Python Random Number Generator

This app accepts in a minimum and maximum number, then returns a number between that range.


## 1. Build the image
````
docker build . -t python-randnum
````

## 2. Run a container from the image we built 

````
docker run -it --rm --name python-randnum-app python-randnum
````

- `docker run` creates and starts the container with the CMD found in Dockerfile (in this case, it's `python rng.py`)
- `-it` there are two flags here – `-i` runs it in _interactive_ mode so that the app can accept inputs. `-t` makes the container start look like a _terminal_ connection session, tells it that its input is a terminal (commands treat input different if it's a terminal) More on this [here](https://stackoverflow.com/questions/30137135/confused-about-docker-t-option-to-allocate-a-pseudo-tty).
- `--rm` will _remove_ the container when it stops running
- `--name python-randnum-app` (optional) _names_ the container.
- Finally, `python-randnum` is the name of the image the container is being run from


## 3. If successful, you should see the following output:

````
Please enter the min number:  
````

Proceed to enter a number...

````
Please enter the min number: 4
Please enter the max number: 10
8
````



## 4. When you're done, stop the container.
````
docker stop python-randnum-app
````

Note: if you did not name the container when you did `docker run` in step 2, you will need to run `docker ps` to find that container and replace `python-randnum--app` with the container id from there.  