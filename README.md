# How to Speedrun Deploy React.js 17 with ec2 linux 2 within 
Watch it here   
React.js 17.0.1  
Since Nov 18, 2020  

---  
```sh
$ sudo yum update -y  
$ sudo yum clean metadata  
```


**Dependencies installation will take some time. After than set proper permissions on files.**  
```sh
$ sudo chown -R ec2-user:apache /var/www  
$ sudo chmod 2775 /var/www && find /var/www -type d -exec sudo chmod 2775 {} \;  
$ find /var/www -type f -exec sudo chmod 0664 {} \;  

$ cd /var/www/html  
$ composer create-project --prefer-dist laravel/laravel speedrun "8.*"  
$ cd /var/www/html/speedrun  
$ composer install  
