# Specify a base image
FROM node:alpine

# Step 2: Download and install dependency
WORKDIR /usr/app
COPY ./simpleweb/package.json /usr/app
RUN npm install
COPY ./simpleweb /usr/app

# Step 3: Tell the image what to do when it starts as container
CMD ["npm", "start"]

#Build: docker build . -t shulander/simpleweb

#Commit: docker commit -c 'CMD ["redis-server"]' 847ac674d84a
# above generates an image from a running container listed by docker ps

#Exec: docker exec -it amazing_mcnulty sh
# above runs a command in a running image

#Mapping a port: docker run -p 8080:8080 shulander/simpleweb
# above route the port from computer 8080 to docker image 8080
