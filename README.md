## Challenge 1 Walkthrough: Setting Up a Simple Static Web Server with Docker

### Step 1: Prepare the Project Directory

I began by navigating to the `challenge1` directory within my local repository, the designated workspace for this Docker challenge.

### Step 2: Add Static Content

Inside the `challenge1` folder, I created a subdirectory called `public`. This is where I placed my `index.html` file, which includes my name and student ID. Additionally, I added any other static assets required for the web page into this directory.

### Step 3: Create a Dockerfile

In the root of the `challenge1` directory, I crafted a `Dockerfile`. This file is crucial as it defines the NGINX base image and instructs Docker to copy the contents of the `public` directory into the image at the expected serving path of NGINX.

### Step 4: Build the Docker Image

With the `Dockerfile` ready, I executed the command below to build my Docker image: docker build -t my-static-server .

This line builds a Docker image tagged as `my-static-server` from the context of the current directory, as denoted by the `.`.

### Step 5: Run the Docker Container

To spin up the image into a container, I used:docker run -d -p 8080:80 my-static-server

This command runs the container in detached mode, maps port 8080 on my host to port 80 in the container, and uses the `my-static-server` image.

### Step 6: Verify the Web Server

I then verified the operation of the web server. Opening a web browser, I navigated to `http://localhost:8080/`, where I was greeted with the static content, confirming that the web server was running as intended.

### Step 7: Push to GitHub

After verifying that my local setup was functioning correctly, I committed the `Dockerfile` and the `public` directory to my GitHub repository. To showcase the successful setup, I also uploaded the screenshot as `proof.png` into the repository. I then pushed all these changes to ensure that the repository was updated and the content was under version control. The `proof.png` can be viewed directly in the repository at the following link:

![Proof of Web Server](https://github.com/Ojifu/docker-challenge-template/blob/main/PROOF.png)

### Step 8: Document and Submit

The final step involved documenting the process. In a `README.md` file, I embedded the `PROOF.png` screenshot as evidence:

This image is a testament to the functioning server delivering the expected static page.

### Conclusion

The static content is now successfully being served through a Docker container, and the entire setup has been meticulously documented and pushed to GitHub. My submission on D2L included the repository link and the screenshot as proof of completion.

## Challenge 2 Walkthrough: Creating a Dynamic Application with Docker

### Introduction

In this challenge, my objective was to create a dynamic Node.js application with a Dockerfile to expose API endpoints and use `docker-compose.yml` to orchestrate the application and webserver using Docker Compose.

### Steps

1. I started by using the provided `challenge2` directory as my working directory.
2. From the provided `challenge2.zip` file, I extracted all the necessary files into the `challenge2` directory.
3. I created a Dockerfile to containerize the Node.js application, ensuring it was configured to expose the right ports and build the server's environment.
4. Following the Dockerfile, I crafted a `docker-compose.yml` that defines two services:
   - An `nginx` service to act as a reverse proxy, set to listen on port 8080.
   - A `node_app` service to run the Node.js application, built from the Dockerfile.
5. I ran `docker-compose up` to start the multi-container application and confirmed that both services were up and running properly.
6. To test the application, I opened a web browser and navigated to `http://localhost:8080/api/books`, which should display a JSON response with a list of books.
7. If any service didn't run as expected, I made necessary adjustments, tested again, and verified the correct response.
8. Once confirmed working, I committed the Dockerfile and `docker-compose.yml` to the remote repository.

### Expected Outcomes

- A successful request to `http://localhost:8080/api/books` would return a JSON response with all the book entries.
- For a specific book, a request to `http://localhost:8080/api/books/1` would return the details for that specific book.

### Problems

A lot of the problems I had with this were because of incorrect directory. I was having troubles displaying the api but after troubleshooting I was able to correctly direct it and display the expected outcome of the authors, book, id, and title.

### Conclusion

The dynamic Node.js application was successfully dockerized, and the endpoints were correctly exposed and accessible through NGINX. The Docker Compose tool used both services . All steps and outcomes were documented and validated and the repository's URL was submitted along with the required documentation on D2L.
