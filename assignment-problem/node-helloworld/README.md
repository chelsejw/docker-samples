# [Node] Hello World

## 1. Create image and run the container
```
docker build -t node-helloworld .
docker run --rm -d -p 3000:3000 --name node-helloworld-app node-helloworld 
```

## 2. View app on http://localhost:3000


## 3. Stop the container with

````
docker stop node-helloworld-app
````