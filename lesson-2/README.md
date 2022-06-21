# Lesson 2: Using a Dockerfile to create our own image

This is where Docker gets immediately more fun! We're going to create our own image so that we can use the image on our 
web server online to serve our site.

# Creating your image:
After we've downloaded or created our Dockerfile we can run the following command to create our image from the Dockerfile's
specifications.

docker build -t my-nginx-image-with-content:latest .


# Running your image:
Once the image is created, we can now run a container using the newly created image. The --name tag simply
allows us to name the container to make it easily readable. The --rm flag will delete this container when we stop
it. 

docker container run --name my-container-name --rm -d -p 80:80 my-nginx-image-with-content:latest


## Explanation

