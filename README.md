# Dockerfile for DVWA

The Damn Vulnerable Web App is a great project to help teach developers and pen-testers.
http://www.dvwa.co.uk/

```
docker run --rm  --name dvwa -p 80:80 -p 3306:3306 originalsix/docker-dvwa
```

Go to the docker machine URL at port 80 (e.g. http://192.168.99.100/ ) and you will be directed to the setup page.
Click the 'Create / Reset Database' button, and you will be redirected to the login page.
The web app login is admin/password

You can override the default mysql password with the MYSQL_PASS env variable.
The Captcha keys can be set with the CAPTCHA_PUB and CAPTCHA_PRIV env variables.
Example:

```
docker run --rm  --name dvwa -p 80:80 -p 3306:3306 -e CAPTCHA_PUB='6L7qHSITAA77AHkGodQrMAY77FKTZKhT7777wK6s' -e CAPTCHA_PRIV='6L7qHSITA77AAG_f5lAN777786ZqhS8rREkf4bfs' -e MYSQL_PASS="p@ssw0rd" originalsix/docker-dvwa 
```
