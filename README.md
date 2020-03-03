# Udagram Image Filtering Microservice

Udagram is a simple cloud application developed alongside the Udacity Cloud Engineering Nanodegree. It allows users to register and log into a web client, post photos to the feed, and process photos using an image filtering microservice.

The project is split into three parts:
1. [The Simple Frontend](https://github.com/ankitshiv/udacity-c2-frontend)
A basic Ionic client web application which consumes the RestAPI Backend. 
2. [The RestAPI Backend](https://github.com/ankitshiv/udacity-c2-restapi), a Node-Express server which can be deployed to a cloud service.
3. [The Image Filtering Microservice](https://github.com/ankitshiv/image-filter-starter-code), the final project for the course. It is a Node-Express application which runs a simple script to process images.

## Links
1. s3 bucket served static website (simple frontend) - http://udashivharefrontend.s3-website.us-east-2.amazonaws.com
2. Image service URL interfaced with Route53 Domain name - http://image-service.drigbhu.com; use /filterimage?image_url={{}} to get filtered image
3. Udacity-c2-restapi with updated endpoints interfaced with Route53 Domain name -  http://udagram-backend.drigbhu.com; refer to [link](https://github.com/ankitshiv/image-filter-starter-code) for endpoint info

## Tasks completed:

1. new endpoint created and the app is served on EBS - image-filter-starter-code-dev22222222.us-east-1.elasticbeanstalk.com
2. created endpoint can be found here - https://github.com/ankitshiv/image-filter-starter-code/blob/master/src/server.ts#L16
3. new endpoint in rest api with required auth created - https://github.com/ankitshiv/udacity-c2-restapi/blob/master/src/controllers/v0/feed/routes/feed.router.ts#L55
4. image service being served using custom domain name - http://image-service.drigbhu.com
5. Deployment screenshot added

### Setup Node Environment

You'll need to create a new node server. Open a new terminal within the project directory and run:

1. Initialize a new project: `npm i`
2. run the development server with `npm run dev`

### Create a new endpoint in the server.ts file

The starter code has a task for you to complete an endpoint in `./src/server.ts` which uses query parameter to download an image from a public URL, filter the image, and return the result.

We've included a few helper functions to handle some of these concepts and we're importing it for you at the top of the `./src/server.ts`  file.

```typescript
import {filterImageFromURL, deleteLocalFiles} from './util/util';
```

### Deploying your system

Follow the process described in the course to `eb init` a new application and `eb create` a new environment to deploy your image-filter service! Don't forget you can use `eb deploy` to push changes.

## Stand Out (Optional)

### Refactor the course RESTapi

If you're feeling up to it, refactor the course RESTapi to make a request to your newly provisioned image server.

### Authentication

Prevent requests without valid authentication headers.
> !!NOTE if you choose to submit this, make sure to add the token to the postman collection and export the postman collection file to your submission so we can review!

### Custom Domain Name

Add your own domain name and have it point to the running services (try adding a subdomain name to point to the processing server)
> !NOTE: Domain names are not included in AWS’ free tier and will incur a cost.
