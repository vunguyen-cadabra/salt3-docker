Docker setup
===============

The Docker environment project.

## Directory structure
```
├─ docker-compose.yml
│
├─ apache
│   └─ vhost.conf
│
├─ centos-apache-php
│   └─ Dockerfile
│
├─ .env.example
│
├─ .gitignore
│
```

## Setup manual
**1. Install Docker Desktop on Windows**:

- Download Docker Desktop for Windows. </br>
  https://hub.docker.com/editions/community/docker-ce-desktop-windows/

(*) Requires Microsoft Windows 10 Professional or Enterprise 64-bit, or Windows 10 Home 64-bit with WSL 2.

**2. Modify project path**

Copy and rename the '.env.example' file to '.env'.

Modify the source directory in .env file.
```
SOURCE_PATH=<SOURCE DIRECTORY>
```

- Application will be mounted to `/opt/www/salt3`
 
You may modify project paths <SOURCE DIRECTORY> in above directory with your local paths.

Eg:
```
SOURCE_PATH=../salt3
```

- Modify others configurations if needed.</br>

Eg: you can modify the port number of http/https instead of the default configuration shown below.
```
APP_PORT=80
```

**3. Build docker**

By using window command line ..etc<br />

1/ Go to docker's directory.<br />
2/ Build image and Build containner.																				
```bash
docker-compose up -d
```

if it's all successed, all the services are running as image below
![Mount](wiki/docker-desktop.JPG)

**4. Add vhost salt3.local vaf api.salt3.local**
* open hosts tại C:\Windows\System32\drivers\etc\
* thêm dòng mới 
    C:\Windows\System32\drivers\etc
```
127.0.0.1 salt3.local api.salt3.local
```		

**4. Access local site**

http://salt3.local/

* if the default port 80 has modified in .env file, it's must be specified in the url properly.

## Useful commands inside container

Show docker images (run on host machine)
```bash
docker ps
```		
