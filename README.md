# OHIF Viewer Deployment

This README provides instructions for deploying the OHIF (Open Health Imaging Foundation) Viewer using Docker.

## Steps

1. Clone the repository:
git clone https://github.com/OHIF/Viewers.git
cd Viewers
Copy
2. Build the Docker image:
docker build . -t ohif-viewer-image
Copy
3. Run the Docker container:
   
`docker run -d -p 3000:80/tcp -v /home/ec2-user/ohif-hctp/default.js:/usr/share/nginx/html/app-config.js --name ohif-viewer-container ohif-viewer-image`


This command does the following:
- Runs the container in detached mode (`-d`)
- Maps port 3000 on the host to port 80 in the container
- Mounts the local `default.js` file to `/usr/share/nginx/html/app-config.js` in the container
- Names the container `ohif-viewer-container`
- Uses the `ohif-viewer-image` we built in step 2

4. Access the OHIF Viewer:
Once the container is running, you can access the OHIF Viewer by navigating to `http://localhost:3000` in your web browser.

## Note

Ensure that the path `/home/ec2-user/ohif-hctp/default.js` exists on your host machine and contains the necessary configuration for the OHIF Viewer.

For more information about the OHIF Viewer and its configuration options, please refer to the official documentation at https://docs.ohif.org/
