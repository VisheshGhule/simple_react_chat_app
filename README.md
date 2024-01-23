# ✨️ Deploying a fullstack React Application on AWS EC2


### Set up an AWS EC2 instance

1. Create an EC2 instance
    - Select an OS image - Ubuntu
    - Create a new key pair & download `.pem` file
    - Instance type - t2.micro
2. Connecting to the instance using ssh
```
ssh -i instance.pem ubunutu@<IP_ADDRESS>
```

### Configuring Ubuntu on remote VM

1. Updating the outdated packages and dependencies
```
sudo apt update
```
2. Install nginx for high-performance web serving, efficient load balancing, and secure SSL/TLS termination.
```
sudo apt install nginx
```
3. Install nodejs it is required to run the server-side code of your application.
```
sudo apt install nodejs -y
```
4. Install nodejs npm(Node Package Manager). npm is used to manage and install the dependencies of your Node.js application, including those required for your React front-end.
```
sudo apt install nodejs npm
```
5. Install pm2 it is a process manager for Node.js applications
```
sudo npm install pm2@latest -g
```


### Deploying the project on AWS

1. Clone this project in the remote VM
```
git clone https://github.com/verma-kunal/AWS-Session.git
```
2. Install npm first in the client directory and then in the server directory
```
npm install
```
3. Start Application
```
pm2 start app.js --name <chat_app>
```
4. Do pm2 logs 0 it helps identify issues & debug errors.
```
pm2 logs 0
```
5. If you get any error then do ''' npm i express '''
6. 
