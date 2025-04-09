
<h1 align="center" style="color:green">ZD Lab Installation for Pentest</h1>

## <code style="color:black ">* Steps for Lab Installation</code>

<code style="color:green"> 1.Install docker software in Linux</code>

2. Pull the docker image 
3. kill server
4. Scripting
5. 


## <code style="color:green"> Install Docker in Linux</code>


`sudo apt install docker.io`

## Enable Docker

`sudo systemctl enable docker --now`


<p style="color:black">You can now get started with using docker, with sudo. If you want to add yourself to the docker group to use docker without sudo, an additional step is needed:???</p>

`sudo usermod -aG docker $USER`



## Pull the docker imag and install it

> ## Interactive mode

> `sudo docker run -p 8080:80 -it zdresearch/advanced-web-hacking http://localhost:8080`

> ## Demon Mode
> `sudo docker run -p 8080:80 -td zdresearch/advanced-web-hacking http://localhost:8080`

## How to kill server

`sudo docker kill imageid`