# How to Speedrun Deploy React.js 17 with ec2 linux 2 within 
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
$ npm -v
7.0.8
$ npx -v
7.0.8
$ npm install pm2@latest -g
```

**Dependencies installation will take some time. After than set proper permissions on files.**  
```sh
$ sudo chown -R ec2-user:apache /var/www  
$ sudo chmod 2775 /var/www && find /var/www -type d -exec sudo chmod 2775 {} \;  
$ find /var/www -type f -exec sudo chmod 0664 {} \;  

