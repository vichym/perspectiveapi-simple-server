# A Simple Server for the Perspective API

This is a simple server used to make calls to Persepective API to evaluted comment from [Feedz](https://github.com/NatthaponSoisangwan/django-react). It provides proxy to the API in a way that enables the API-key to be kept private. This server is borrowed from [conversationai](https://github.com/conversationai/perspectiveapi-simple-server). 

## Quickly trying it out
Follow the steps below: 
```
# Install dependencies
yarn install

# Make sure the build directory is setup (has at least a copy of the template config)
yarn run setup

# Build the code (in build/)
yarn run build

# Start a dev server locally on port 8080
yarn run start-dev
```
Now you can visit `http://localhost:8080/` and you should get a "hello world!" page.

## Configuring the server

To configure the server, create a `server_config.json` file with the following
fields.

*  "port": The port to run on. The default is 8081 for development and 8080 for
   production if this is left empty.

*  "staticPath": The path where the static html/css/js resources are located.
   Note that this path is relative to the directory of the run_server.js file, which
   is in your project's `node_modules`
   `node_modules/@conversationai/perspectiveapi-simple-server/build/server/run_server.js`

*  "googleCloudApiKey": The API key for your google cloud project. Please find the API key in the previous README.md of Feedz. 

*  "toxicityAttribute": The name of the attribute to use for toxicity scores. See the [PerspectiveAPI documentation](https://conversationai.github.com/perspectiveapi/) for more details.

*  "recaptchaConfig": An optional configuration for enabling reCAPTCHA v3 verification.
    This is empty by default. The requisite fields for this option are `secretKey` and
    `threshold`. See the `Config` interface in `serving.ts` for more details. We will not need this for this development stage. 

Note: The following can be done with npm as well as yarn, but yarn is
recommended.

To use this server, run:

```bash
yarn add @conversationai/perspectiveapi-simple-server
yarn install
```

This will add the server to your `node_modules` folder.

Then, to run the server, call:

```bash
node node_modules/@conversationai/perspectiveapi-simple-server/build/server/run_server.js server_config.json
```

## Notes
This is example code to help experimentation with the Perspective API; it is not an official Google product. 
