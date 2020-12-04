FROM node

# This tells Docker all subsequent commands should executed in this folder.
WORKDIR /app

COPY package.json .

# which files from our local machine should go into the image?

RUN yarn install

# You do not RUN node server.js here -- the server should only be run from the container. This is just the blueprint.

COPY . .

# The first dot = all files in this directory should be copies
# Second dot is the image's internal path where the files should be stored - since WORKDIR is already /app, it will copy files to /app


EXPOSE 80

# Because the app is listening on port 80 but it is the ISOLATED container's port 80 - so we need to expose the container's port 80 to be able to access the app.

# However this doesn't do much -- it's optional, but just for documentation. When executing the docker run command, you should still run it with the -p (publish command)

# docker run -p 3000:80 imageNumber

# 3000:80 is local_port_you_want_to_use:internal_docker_port_used

CMD ["node", "server.js"]

# CMD is executed when a container is started from the image. The commands must be in an array form.
# If no CMD is specified, the CMD of the base image (in this case it'll be Node) will be executed.
# If you have no CMD and no base image you will get an error.