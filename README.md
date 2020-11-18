# How to Speedrun Deploy create-react-app React.js 17 with ec2 linux 2 within 
Watch it here   
React.js 17.0.1, Node.js v15.2.1, npm 7.0.8, npx 7.0.8
Since Nov 18, 2020  

---  
```sh
$ sudo yum update -y  
$ sudo yum clean metadata  
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
$ . ~/.nvm/nvm.sh
$ nvm install node
$ node -e "console.log('Running Node.js ' + process.version)"
Running Node.js v15.2.1
$ sudo amazon-linux-extras list
$ sudo amazon-linux-extras install -y nginx1 or sudo amazon-linux-extras enable nginx1 -y  
$ npx create-react-app my-app
$ npm start
```
