1. Create react app using `npm create-react-app [app-name]`. Put both lock files in the **.gitignore**.
2. Install Docker for Mac using a [Mac Stable Release]( https://docs.docker.com/v17.12/docker-for-mac/install/). 
3. Write **Dockerfile** to create a web server: 

<pre><code>
# call node image with appropriate tag
FROM node:10
# sets the working directory
WORKDIR '/app'

COPY package.json .
RUN npm install
# copy everything contained in dockerfile
COPY . . 
# run dockerfile
CMD ["npm", "start"]
</code></pre>

4. Build the docker image with `docker build . -t [image-name]`.
5. Run the docker using `docker run [image-name]`. In a second terminal, type `docker ps`.
6. Take the STATUS name from the second terminal and run `docker exec -it [STATUS] sh`. For example, STATUS will look similar to a8a1f8a79426. Now start the development server by typing `npm start`. Press `Y`. 



Acknowledgements 
* [Create React App](https://github.com/facebook/create-react-app)
* [How to Deploy React Application on docker?](https://www.youtube.com/watch?v=O3SvhpnSZWY)
* [Learn Docker in 12 Minutes](https://www.youtube.com/watch?v=YFl2mCHdv24)
* [Dockerizing a Node.js web app](https://nodejs.org/de/docs/guides/nodejs-docker-webapp/)

