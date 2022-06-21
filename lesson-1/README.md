# docker-nginx-server

This is the script run the latest version of NGINX and will bind a folder on your localhost to the docker instance. This creates a web server on your localhost! If 
you're on a UNIX based machine (Mac or Linux), you can copy and paste the following code in your terminal. Make sure that you navigate to the folder that your 
website is in, or update the 5th line to be source="$(pwd)"/folder_name


# The Code:

docker run -d &#92; \
  -it &#92; \
  -p 8080:80 &#92; \
  --name yourcontainernamehere &#92; \
  --mount type=bind,source="$(pwd)",target=/usr/share/nginx/html &#92; \
  nginx:latest
  
  
  ## Explanation
  
  
Line 1: "docker run -d" will run the container in detach mode, so the container can run in the background and will free up your shell session.

Line 2: "-it" will initiate a "bash" shell so you can interact with your container and send commands.

Line 3: "-p" will let you access the container on port 80 when you type in localhost:8080 in your browser

Line 4: "--name" will allow you to create a descriptive name for your container. You can start your containers with this name

Line 5: This will bind a folder from your localhost to the container you are creating. You can map a folder and its structure so that updates made on your 
localhost reflect in the container

Line 6: Will use the latest version of nginx as your image. If you don't have the latest image, Docker will download the image when the command is run

