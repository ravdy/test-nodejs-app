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
