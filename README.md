# golang
The Steps for this assignment is as described below with the screen shot

      Creating 3 instance 
      App1:- applicaton node for GO Code Section
      App2:-Application node for Go COde section
      LB:- this is the for showing the "Hi there, I'm served from "server name"" in round robin fashion.
      
      Nginx configuration on LB:
      
        upstream backend  {
          server 172.31.22.180;   #App2
          server 172.31.27.30;    #App1
         }

        server {
                listen 35.154.129.157:80 default_server;
                listen [::]:80 default_server ipv6only=on;
                 listen 80;

                location / {
                proxy_pass  http://backend;
                }
          }
      
       

