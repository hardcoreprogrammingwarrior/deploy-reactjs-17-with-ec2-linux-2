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
$ sudo mkdir /var/www  
$ cd /var/www/  
$ npx create-react-app my-app
$ npm run build
```

```sh
$ sudo vim /etc/nginx/sites-available/default
```

**Add code**  

```blade
server {
     listen 80;  
     server_name _;
     
     location / {
    	     proxy_set_header X-Forwarded-For $remote_addr;
     	proxy_set_header Host $http_host;
          proxy_pass http://3.138.120.99:3000;
     }  
}  
```

**Start nginx**  
```blade
sudo service nginx start
```

**Keep react app running even if your logout of the server**  
```blade
$ cd /var/www/my-app
$ npm install pm2 -g   
$ pm2 list
$ pm2 start --name my-app npm -- start
$ pm2 list
```

**To delete**  
```blade
$ pm2 delete my-app
```
