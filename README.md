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

With my local setup confirmed, I proceeded to commit the `Dockerfile`, the `public` directory, and `proof.png` to my GitHub repository. After committing the changes, I pushed them to ensure that everything was properly version-controlled and accessible online.

### Step 8: Document and Submit

The final step involved documenting the process. In a `README.md` file, I embedded the `PROOF.png` screenshot as evidence:

This image is a testament to the functioning server delivering the expected static page.

### Conclusion

The static content is now successfully being served through a Docker container, and the entire setup has been meticulously documented and pushed to GitHub. My submission on D2L included the repository link and the screenshot as proof of completion.
