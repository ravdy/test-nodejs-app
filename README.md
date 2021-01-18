# Build and Deploy nodejs application on EC2 instance - Freestyle 

# Pre-requisites

1. A Jenkins server 
1. A EC2 instance to install and deploy node.js 

### Setup node.js server 
1. Enable nodejs packages on Linux server 
   ```sh 
   curl -sL https://rpm.nodesource.com/setup_14.x | bash -
   ```

1. Install nodejs
   ```sh 
   yum -y install nodejs
   ```

1. install development tools. 
   ```sh 
   yum groupinstall 'Development Tools'
   ```

Setup Jenkins job 


## Fork nodejs applicaton onto your repository 

Github URL: 

Using simple "hello world" application from the [nodejs.org](https://nodejs.org/en/docs/guides/getting-started-guide/) website





