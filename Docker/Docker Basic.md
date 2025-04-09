

<h1 align="Center">Basic Practical Docker and Containerization</h1>

## What is Docker?

[Referece Photo Link](Ref:https://www.accenture.com/us-en/blogs/software-engineering-blog/shinde-docker-containerization-devops)


## Docker images VS Container



## Install Docker and skopeo on Linux
`sudo apt install docker.io`

`sudo apt install skopeo`

## Enable Docker on linux
`sudo systemctl enable docker --now`

## You can now get started with using docker, with sudo. If you want to add yourself to the docker group to use docker without sudo, an additional step is needed:???

`sudo usermod -aG docker $USER`

# Essential Command

>### Searching Docker image from Repository (DockerHub)
>`sudo docker search imageName` 

>### Pulling (Downloading) images to local Computer
>`sudo docker pull imageName`

>### How to look local images
>`sudo docker images`
>
>### How to inspect Local image (Show image detail infromation)
>`sudo docker inspect ImageID`
>
>### How to inspect remote registory images
>`skopeo inspect docker://mysql`


## How to run local container images
```
sudo docker images
sudo docker run imageid
```
## How to find running container (Docker see container as process)
`sudo docker ps`

## How to find all container (including not running container)
`sudo docker ps -a`

## Checking Docker Resource Usage
`sudo docker stats`

<h1 align="Center"> Container Mangement with Portainer (Web App)</h1>

## Install portainer docker file

`docker search portainer`

`docker pull portainer/portainer-ce`


## Run portainer docker file


`docker run --name portainer -p 9000:9000 -v "/var/run/docker.sock:/var/run/docker.sock"`

### Notes
> * you can use my portianer script to run portainer
> * please disconnect VPN otherwise localhost did not work 
> * you can use docker ip and port instead of localhost and local port

---

---

### 🐋 **Docker Basic Commands**

#### 1. 🔍 **Docker Version Check**

```bash
docker --version
```

Docker ရဲ့ Version ကိုစစ်ဆေးဖို့အသုံးပြုတယ်။

---

#### 2. 📂 **Docker Images List**

```bash
docker images
```

Download လုပ်ထားတဲ့ Image List တွေကို ပြသပေးတယ်။

---

#### 3. 🚀 **Pull Docker Image**

```bash
docker pull ubuntu:latest
```

Docker Hub မှ Ubuntu ရဲ့ Latest Version ကို Download လုပ်တာပေါ့။

---

#### 4. 🏃 **Run Docker Container**

```bash
docker run -it --name mycontainer ubuntu bash
```

- `-it` -> Interactive Mode နဲ့ Terminal ကိုအသုံးပြုနိုင်စေတယ်။
- `--name` -> Container ကိုအမည်ပေးဖို့။
- `ubuntu` -> Image Name
- `bash` -> Shell Prompt ထဲသို့ ဝင်ရန်။

**Example:**

```bash
docker run -d -p 8080:80 nginx
```

- `-d` -> Detached Mode (Background မှာ Run လုပ်တာ)
- `-p` -> Port Mapping (Host Port 8080 ကို Container Port 80 နဲ့ချိတ်ဆက်)
- `nginx` -> NGINX Server Image

---

#### 5. 🔄 **List Running Containers**

```bash
docker ps
```

ပြောင်းလဲနေတဲ့ (Running) Containers တွေကိုပြပေးတယ်။

---

#### 6. 🗑️ **Stop Docker Container**

```bash
docker stop mycontainer
```

Container ကို Stop လုပ်တာ။

---

#### 7. ❌ **Remove Docker Container**

```bash
docker rm mycontainer
```

Stopped ဖြစ်တဲ့ Container ကိုဖျက်သိမ်းခြင်း။

---

#### 8. 🗑️ **Remove Docker Image**

```bash
docker rmi ubuntu
```

Docker Image ကိုဖျက်ခြင်း။

---

#### 9. 💻 **Access Running Container**

```bash
docker exec -it mycontainer bash
```

Running ဖြစ်တဲ့ Container ထဲကို ဝင်ရောက်အသုံးပြုနိုင်တယ်။

---

#### 10. 📝 **Docker Logs**

```bash
docker logs mycontainer
```

Running Container ရဲ့ Logs တွေကိုကြည့်ရှုနိုင်တယ်။

---

#### 11. 📂 **Save Docker Image**

```bash
docker save -o myimage.tar ubuntu:latest
```

Docker Image ကို TAR ဖိုင်အဖြစ် Export လုပ်ခြင်း။

---

#### 12. 🚚 **Load Docker Image**

```bash
docker load -i myimage.tar
```

Save လုပ်ထားတဲ့ TAR ဖိုင်မှ Docker Image ကို Load ပြန်လုပ်ခြင်း။

---

#### 13. 🔎 **Inspect Container Details**

```bash
docker inspect mycontainer
```

Container ရဲ့ နေရာချထားမှု၊ Network၊ Volume စသည့် အချက်အလက်တွေကို စစ်ဆေးဖော်ပြခြင်း။

---

### 📝 **Basic Example**

1. NGINX Server Run လုပ်မယ်

```bash
docker run -d -p 8080:80 --name mynginx nginx
```

2. Running Status စစ်မယ်

```bash
docker ps
```

3. Web Browser မှာ စစ်ဆေးပါ

- URL: `http://localhost:8080`

4. Stop လုပ်မယ်

```bash
docker stop mynginx
```

5. Remove လုပ်မယ်

```bash
docker rm mynginx
docker rmi nginx
```

---
