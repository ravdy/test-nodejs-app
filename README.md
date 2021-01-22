# Build and Deploy nodejs application on EC2 instance - Freestyle 

# Pre-requisites

1. A Jenkins server 
1. A EC2 instance (Application server) and deploy node.js 

### Setup nodejs packages on jenkins (needed for build) and application server (needed to deploy)
1. Enable nodejs packages on Linux server 
   ```sh 
   curl -sL https://rpm.nodesource.com/setup_15.x | bash -
   ```
1. install development tools. 
   ```sh 
   yum groupinstall 'Development Tools'
   ```

1. Install nodejs
   ```sh 
   yum -y install nodejs
   ```


Setup Jenkins job 


## Fork nodejs applicaton onto your repository 

Github URL: https://github.com/ravdy/nodejs.git

Using simple "hello world" application from the [nodejs.org](https://nodejs.org/en/docs/guides/getting-started-guide/) website


## On Jenkins GUI 

1. Create the new FreeStyle Project 
   ```sh
   Git URL - https://github.com/ravdy/nodejs.git
   ```
  BUILD --> Execute Shell npm install
   ```sh 
   npm install
   tar czf easyio.tar-$BUILD_NUMBER.gz node_modules main.js package.json public LICENSE
   ```

## To Deploy on nodejs application server 

1. Download `publish over ssh` plugin and configure nodejs server 
   ```sh
   Manage Jenkins --> Manage Plugins --> Available --> Search for "publish Over SSH" and install

   Manage Jenkins --> configure System --> Publish over SSH
   `key` - Private key (.pem key which is used to login nodejs server)
   SSH Server 
        Name - nodejs server 
        HostName - <nodejs server Private IP> (you can still use public IP too. But it get changed every time when you stop and start of the server)
        Username - ec2-user 
        Remote Directory - /tmp (make sure you have access to `Remote Directory`. /tmp is accessable by any user by default)
        Click Save and Apply
   ```
  

1. Update the jenkins job to deploy on nodejs server 

   ```sh 
   Post build actions 