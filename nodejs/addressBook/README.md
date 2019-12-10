# NodeJS Address Book
This is a simple NodeJS Express webserver hosting a static website with an API. If you navigate to the root direcotry using a web browser, you will get a table of all the people in your address book. If you adjust the address-book.json file, you can add or remove users from your app.

There's also an API for testing the app further after deployment.

## Setting up the project
To get started, you will need to complete the following tasks to start the project.

1. Download and install NodeJS if you havent already
2. Clone the repo to your computer
```
git clone git@github.com:tpeterson66/portable.git
```
3. Change directories to protable/nodejs/addressBook
4. Install required packages
```
npm install
```
5. Configure a .env file to include the following parameters. This is just a file in the /portable/nodejs/addressBook directory with a name of .env
```
PORT=3000
TOKEN="<FAKEJSON.COM TOKEN>" # minus the <> of course ;)
```

## API Documentation

### GET /api/fresh
This will return 10 fresh records from the FakeJSON API. This requires that you have a fakejson.com account and that you have saved your token in the .env file. This will return an array of 10 objects including name, email, and phone.

### GET /api/bulk
This endpoint is intended to be used for bulk testing against the API if you want to try and stress the API. This will return the items in the address-book.json file, assuming the file is still a JSON array of Objects!

### GET /api/status
This endpoint will return the hostname and uptime of the system running the app. This can be used to identify which container or VM is running your app when messing with those technologies!

## Next Steps
Once you get the app up and running, look into the following things!
1. Getting the app running in a docker container
2. Use docker-compose to spin up a few containers of the app (mess with the status api endpoint)
3. Put a load-balancer in front of your application and containers
4. Mess with CI/CD to deploy the app
5. Get the app running in Kubernetes and public accessible
6. Secure the app with HTTPS (LetsEncrypt)