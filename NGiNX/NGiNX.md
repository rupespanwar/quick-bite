# Nginx installation using pkg manager

        * ssh root@ip-of-remote-machine
        * apt install nginx

        * systemctl start nginx
        * systemctl status nginx
        *  ifconfig 

# Installation using source code
        * ssh root@ip-of-remote-machine
        * apt-get update
        * wget nginx-download-link # https://nginx.org/download/nginx-1.21.1.tar.gz
        * wget https://nginx.org/download/nginx-1.21.1.tar.gz
        ![image](https://user-images.githubusercontent.com/75510135/128177664-722d6837-69a1-48b5-b41e-432a2f492c55.png)
        * tar -zxvf tar-file-name 
        * cd nginx-1.21.1
        * apt-get install build-essential
        * ./configure
        * install PCR libs
        * ./configure
        * ./configure # http://nginx.org/en/docs/configure.html
          --sbin-path=/usr/local/nginx/nginx
          --conf-path=/usr/local/nginx/nginx.conf
          --pid-path=/usr/local/nginx/nginx.pid
          --with-http_ssl_module
          --with-pcre=../pcre-8.44
          --with-zlib=../zlib-1.2.11
        * make
        * make install
        * nginx -v
        * nginx
        * ps -ef | grep nginx
        # list master/worker process
        * ifconfig => curl http://ip-address
        
# Building NGINX from Source Code

1. Update Packages

  * Ubuntu - apt-get update
  * CentOS - yum update

2. Download the NGINX source code from nginx.org
  * https://nginx.org/download/nginx-1.19.1.tar.gz

3. Unzip the file.
  * tar -zxvf nginx-1.19.1.tar.gz

4. Configure source code to the build.
  * ./configure

4. Install code compiler
  * Ubuntu : apt-get install build-essential
  * CentOS : yum groupinstall "Development Tools"

5. Configure source code to the build.
  * ./configure

6. GET Support Libraries
  * Ubuntu : apt-get install libpcre3 libpcre3-dev zlib1g zlib1g-dev libssl-dev make
  * CentOS : yum install pcre pcre-devel zlib zlib-devel openssl openssl-devel make

7. Execute configuration again
  * ./configure --sbin-path=/usr/bin/nginx --conf-path=/etc/nginx/nginx.conf --error-log-path=/var/log/nginx/error.log --http-log-path=/var/log/nginx/access.log --with-pcre --pid-path=/var/run/nginx.pid --with-http_ssl_module

8. Compile and install Nginx
  * make    

# Add NGINX As Service in OS

Add NGINX Process in Systemd Services to make the WebServer Resilient.

1. NGINX Init Services File.
  * https://www.nginx.com/resources/wiki/start/topics/examples/systemd/


2. Start Service
  * systemctl start nginx

3. Stop Service
  * systemctl stop nginx

4. Restart-Service
  * systemctl restart nginx

5. Check Service Status
  * systemctl status nginx

6. Enable service, auto-start on boot
  * systemctl enable nginx 

# Add NGiNX as Service
* https://www.nginx.com/resources/wiki/start/topics/examples/systemd/
![image](https://user-images.githubusercontent.com/75510135/128181776-ada65880-d26b-44d1-867c-cd9131d2a30f.png)
 
 * touch /lib/systemd/system/nginx.service
 * vi /lib/systemd/system/nginx.service
 * paste given script
 **minor changes in the default script**
![image](https://user-images.githubusercontent.com/75510135/128182263-28cad09c-4479-4498-b268-b4a7e74d424d.png)
 * nginx
 * systemctl start nginx
 * systemctl status nginx
![image](https://user-images.githubusercontent.com/75510135/128182963-5b48bcca-1c3f-4c9a-9193-11340495dac5.png)
 * **systemctl enable nginx**

**NGiNX help***
* nginx -h










