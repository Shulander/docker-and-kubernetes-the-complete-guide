FROM alpine

# Step 2: Download and install dependency
RUN apk add --update redis
RUN apk add --update gcc

# Step 3: Tell the image what to do when it starts as container
CMD ["redis-server"]

#Build: docker build . -t shulander/redis

#Commit: docker commit -c 'CMD ["redis-server"]' 847ac674d84a
# above generates an image from a running container listed by docker ps
