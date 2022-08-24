<h1 align="center">
  <a href="https://littlelink-custom.com/docker"><img width="900" src="https://i.imgur.com/5o0w0jk.png" alt="LittleLink Custom"></a>
</h1>

<h3 align="center">Pull, deploy, enjoy!</h3><br>

<p align="center">
  <a href="#1">About</a> •
  <a href="#2">About LittleLink Custom</a> •
  <a href="#3">Pull</a> •
  <a href="#4">Supported Architectures</a> •
  <a href="#5">Deployment</a> •
  <a href="#6">Updating</a> •
  <a href="#7">Build</a> •
  <a href="#8">Reverse Proxy</a>
</p><br>

<p align="center">
  <strong><a href="https://demo.littlelink-custom.com/">Live Demo</a></strong>
</p>

<p align="center">
<a href="https://github.com/JulianPrieber/llc-docker/stargazers"><img src="https://img.shields.io/github/stars/julianprieber/llc-docker?logo=github&style=flat&logo=appveyor&label=star%20this%20project"></img></a>
<a href="https://hub.docker.com/r/julianprieber/littlelink-custom"><img src="https://img.shields.io/docker/stars/julianprieber/littlelink-custom?&style=flat&logo=appveyor&label=docker%20hub"></img></a>
<a href="https://discord.littlelink-custom.com"><img src="https://img.shields.io/discord/955765706111193118?color=4A55CC&label=Discord&logo=discord&style=flat&logo=appveyor"></img></a>
<a href="https://github.com/sponsors/julianprieber"><img src="https://img.shields.io/github/sponsors/JulianPrieber?color=BF4B8A&logo=githubsponsors&style=flat&logo=appveyor=Sponsor%20on%20Github"></img></a>
<a href="https://patreon.com/julianprieber"><img src="https://img.shields.io/endpoint.svg?url=https%3A%2F%2Fshieldsio-patreon.vercel.app%2Fapi%3Fusername%3Djulianprieber%26type%3Dpatrons&style=flat&logo=appveyor"></img></a>
</p>

<p align="center">
  <a href="https://hub.docker.com/r/julianprieber/littlelink-custom"><img src="https://i.imgur.com/u9W2tg1.png" alt="Docker Hub" width="280" ></a>
</p>

<a name="1"></a>
## About

The official docker version of [LittleLink Custom](https://github.com/JulianPrieber/littlelink-custom). This docker image is a simple to set up solution, containing everything you need to run LittleLink Custom.

The docker version of LittleLink Custom retains all the features and customization options of the [original version](https://github.com/JulianPrieber/littlelink-custom).

This docker is based on [Alpine Linux](https://www.alpinelinux.org/), a Linux distribution designed to be small, simple and secure. The web server is running [Apache2](https://www.apache.org/), a free and open-source cross-platform web server software. The docker comes with [PHP 8.0](https://www.php.net/releases/8.0/en.php) for high compatibility and performance.

#### Using the docker is as simple as pulling and deploying.

<br>

<a name="2"></a>
## About LittleLink Custom

<p align="center">
<img width="450" src="https://i.imgur.com/mtP2K3K.png">
</p>

<p align="center">
<strong>LittleLink Custom is a highly customizable link sharing platform with an intuitive, easy to use user interface.</strong>
    
<p align="center">LittleLink Custom allows you to create a personal profile page. Many social media platforms only allow for one link. With this, you can have all the links you want clickable on one site. Set up your personal site on your own server in a few clicks.</p>
</p>

<br>

<p align="center">
<strong>Learn more about LittleLink Custom, and all the features here:</strong>
</p>

<br>

<p align="center">
  <a href="https://github.com/JulianPrieber/littlelink-custom"><img src="https://i.imgur.com/c1PYOs6.png" alt="About" width="310" ></a>
</p>

<br>

<a name="3"></a>
## Pull

`docker pull julianprieber/littlelink-custom`

<br>

<a name="4"></a>
## Supported Architectures

- [`linux/amd64`](https://hub.docker.com/r/julianprieber/littlelink-custom/tags)
- [`linux/arm/v6`](https://hub.docker.com/r/julianprieber/littlelink-custom/tags)
- [`linux/arm/v7`](https://hub.docker.com/r/julianprieber/littlelink-custom/tags)
- [`linux/arm64`](https://hub.docker.com/r/julianprieber/littlelink-custom/tags)

<br>

<a name="5"></a>
## Deployment

You may change port *80*, *443* to your preferred values.  

Both HTTP and HTTPS are supported and exposed by default.

### Optional environment variables

- `SERVER_ADMIN` (the email, defaults to `you@example.com`)
- `HTTP_SERVER_NAME` (the [server name](https://httpd.apache.org/docs/2.4/fr/mod/core.html#servername), defaults to `localhost`)
- `HTTPS_SERVER_NAME` (the [server name](https://httpd.apache.org/docs/2.4/fr/mod/core.html#servername), defaults to `localhost`)
- `LOG_LEVEL` (the [log level](https://httpd.apache.org/docs/2.4/fr/mod/core.html#loglevel), defaults to `info`)
- `TZ` (the [timezone](https://www.php.net/manual/timezones.php), defaults to `UTC`)
- `PHP_MEMORY_LIMIT` (the [memory-limit](https://www.php.net/manual/ini.core.php#ini.memory-limit), defaults to `256M`)
- `UPLOAD_MAX_FILESIZE` (the [upload_max_filesize](https://www.php.net/manual/en/ini.core.php#ini.upload-max-filesize), defaults to `8M`)

<br>

#### Deploy

<pre>
docker run --detach \
    --name littlelink-custom \
    --publish 80:80 \
    --publish 443:443 \
    --restart unless-stopped \
    julianprieber/littlelink-custom
</pre>

<br>

#### Custom deployment

<pre>
docker run --detach \
    --name littlelink-custom \
    --hostname littlelink-custom \
    --env HTTP_SERVER_NAME="www.example.xyz" \
    --env HTTPS_SERVER_NAME="www.example.xyz" \
    --env SERVER_ADMIN="admin@example.xyz" \
    --env TZ="Europe/Berlin" \
    --env PHP_MEMORY_LIMIT="512M" \
    --env UPLOAD_MAX_FILESIZE="16M" \
    --publish 80:80 \
    --publish 443:443 \
    --restart unless-stopped \
    julianprieber/littlelink-custom
</pre>

<br>


#### You can now log in to the Admin Panel, on your defined ports, with the credentials:
-   **email:** `admin@admin.com`
-   **password:** `12345678`

<br>	

### Optional configuration:
Optionally, you can change the app name in your ".env" file in the root directory of your LittleLink Custom installation. At the moment this is set to
APP_NAME="LittleLink Custom" you can change "LittleLink Custom" to what ever you like. This setting defines the page title and welcome message.

For more configuration options, refer to the [documentation](https://littlelink-custom.com/docs/d/configuration-getting-started/).

<br>

<a name="6"></a>
## Updating

When a **new version** is released, you will get an update notification on your Admin Panel.

### Automatic one click Updater
This updater allows you to update your installation with just one click.

<br>	

**How to use the Automatic Updater:**

- To update your instance, click on the update notification on your Admin Panel.

- Click on “Update automatically” and the updater will take care of the rest.

<br>

<a name="7"></a>
## Build

**If you wish to build or modify your own docker version of LittleLink Custom, you can do so with the instructions below:**

- Download this GitHub repository as well as the latest release of LittleLink Custom from [here](https://github.com/JulianPrieber/littlelink-custom/releases/latest/download/littlelink-custom.zip).
- Place the downloaded release files directly into the littlelink-custom folder from [this repository](https://github.com/JulianPrieber/llc-docker/archive/refs/heads/main.zip).

From the docker directory, run the command:
<pre>
docker build -t littlelink-custom .
</pre>

<br>

<a name="8"></a>
## Reverse Proxy

<br>

|                   ❌ Invalid setup ❌                    |
| ----------------------------------------------------- |
|<a href="https://github.com/JulianPrieber/llc-docker#8"><img src="https://i.imgur.com/QSCDU6w.png"></a>|

<br>

|                   ⚠️ Incorrect ⚠️                    |                    ✅ Correct ✅                     |  
| ----------------------------------------------------- | ----------------------------------------------------- |
|<a href="https://github.com/JulianPrieber/llc-docker#8"><img width="500" src="https://i.imgur.com/3ellGki.png"></a>|<a href="https://github.com/JulianPrieber/llc-docker#8"><img width="500" src="https://i.imgur.com/EfKRGSJ.png"></a>|
|              Invalid header configuration             |               Valid header configuration              |

<br>

### NGINX:

**Below is an example NGINX setup for a reverse proxy.**
<details><pre>

server {
  listen        443 ssl;
  listen        [::]:443 ssl;
  listen        80;
  listen        [::]:80;
  server_name   your.domain.name;

  location / {
    # Replace with the IP address and port number of your Docker container.
    proxy_pass                          https://127.0.0.1:443;
    proxy_set_header Host               $host;
    proxy_set_header X-Real-IP          $remote_addr;

    proxy_set_header X-Forwarded-For    $proxy_add_x_forwarded_for;
    proxy_set_header X-Forwarded-Proto  https;
    proxy_set_header X-VerifiedViaNginx yes;
    proxy_read_timeout                  60;
    proxy_connect_timeout               60;
    proxy_redirect                      off;

    # Specific for websockets: force the use of HTTP/1.1 and set the Upgrade header
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection 'upgrade';
    proxy_cache_bypass $http_upgrade;
    proxy_set_header X-Forwarded-Proto $scheme;
    
    # Fixes Mixed Content errors.
    add_header 'Content-Security-Policy' 'upgrade-insecure-requests';
  }
}

</pre></details>

<br>
<br>
