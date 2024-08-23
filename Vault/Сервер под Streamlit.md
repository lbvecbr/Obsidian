[Medium](https://medium.com/@linux.franklin/streamlit-with-nginx-a-step-by-step-guide-to-setting-up-your-data-app-on-a-custom-domain-7f5da2d4b3be)
Создаем файл конфигурации streamlit
`~/.streamlit/config.toml`
```
[server]  
port = 8502 # change port number. By default streamlit uses 8501 port  
headless = true # This will eliminate automatically open browser
[browser]  
serverAddress = "your_server_name" # Put your Local IP or Domain Name 
serverPort = 8502
```
Создаем конфиг nginx для своего сайта
`sudo vim /etc/nginx/sites-enabled/your_server_name`
```
server {  
listen 80;  
server_name your_server_name www.your_server_name;  
index index.php index.html index.htm;  
location / {  
proxy_pass http://0.0.0.0:8502/;  
proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;  
proxy_set_header Host $http_host;  
proxy_redirect off;  
proxy_http_version 1.1;  
proxy_set_header Upgrade $http_upgrade;  
proxy_set_header Connection "upgrade";  
	}  
error_page 404 /404.html;  
error_page 500 502 503 504 /50x.html;  
location = /50x.html {  
root /usr/share/nginx/html;  
	}  
}
```
Тестируем кофиг
`sudo nginx -t`
`sudo systemctl start nginx`
`streamlit run [my script].py --server.address 0.0.0.0 --server.port 8502`



