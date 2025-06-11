# 💻 Azure Devops Video Tutorials
<details>

<summary>1. Create a Virtual Machine(VM)</summary>
   - Configure VM with the same settings as in the Screenshots.
   - Save User-Name and Password for later use
   - Stop VM when not in use
   - Delete VM when all tasks listed below are completed
   - In Network Settings Create Inbound Rule for port 8080

<img src="https://github.com/vntkshp/XPMC-tutorial/Screenshorts/VM-Config.jpg" width="300">
<img src="https://github.com/vntkshp/XPMC-tutorial/Screenshorts/VM-Disk.jpg" width="300">
<img src="https://github.com/vntkshp/XPMC-tutorial/Screenshorts/VM-Network.jpg" width="300">


</details>



----------------------------------------------------------


<details>

<summary>2. Create a DevOps Project in Organization</summary>
	- Create New Organisation and Project
	- Give permissions to all members.
</details>




----------------------------------------------------------



<details>

<summary>3. Clone a project to Azure Repos
</summary>
	
   1. Clone ![this](https://github.com/dockersamples/snake-game-tensorflow-docker.git) demo project from github to Repos
   2. Create and Save **Personal Access Tokens** for later use
   3. Create and Save **Git Credentials** for later use
</details>



----------------------------------------------------------




<details>

<summary>5. Run Docker on VM</summary>

**Update your package index**
```
sudo apt update
```

**Install required packages to allow apt to use repositories over HTTPS**
```
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common
```

**Add Docker's official GPG key**
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

**Set up the stable Docker repository**
```
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

**Update the package index again**
```
sudo apt update
```

**Install Docker Engine**
```
sudo apt install -y docker-ce docker-ce-cli containerd.io
```

**Verify Docker installation**
---
sudo docker run hello-world
---

**Clone Repository to VM**
paste git repository link at the end for this to work
```
git clone 
```

**Build image**
```
sudo docker build -t my-image .
```

**Run Docker Image**
```
docker compose up -d
```

**Stop Docker Image**
```
docker compose down
```

**List running docker containers**
```
sudo docker ps
```

</details>



----------------------------------------------------------




<details>

<summary>8. nginx tutorial</summary>

**Install nginx**
```
sudo apt install nginx
```

**Check Version**
```
nginx -version
```

```
cat Dockerfile
```
***Backup nginx.conf**
```
sudo mv /etc/nginx/nginx.conf etc/nginx/nginx.conf.bak
```


**Open nginx.conf**

```
sudo nano etc/nginx/nginx.conf


** Paste this in nginx.conf**
```
events {}

http {
	server {
    		listen 80;

    		location / {
        		proxy_pass http://127.0.0.1:8080;
        		proxy_set_header Host $host;
        		proxy_set_header X-Real-IP $remote_addr;
        		proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    		}
	}
}
```



</details>



----------------------------------------------------------

<details>

<summary>9. Assign VM as Agent
</summary>
	- Create New Self Hosted Agent
	- Assign VM as Self Hosted Agent
	- Create Linux based Agent
	- **Save Access token for later use**

###Use following commands to configure Agent

** **
```
mkdir myagent && cd myagent
```
** **
```
 tar zxvf ~/vsts-agent-linux-x64-4.255.0.tar.gz
```
**To configure Agent **
```
./config.sh
```
**To start Agent **
```
./run.sh
```


</details>


------------------------------------------------------------

<details>

<summary>10. Create an Agent in Azure Pipelines</summary>

   - Search for Organisation in Search bar
   - Create VM by giving the details.
   - Create Project to access DevOps Applications


<img src="https://github.com/user-attachments/assets/6657078f-be16-4679-bb0a-565e6c8e1d0a" width="300">
[![twitter](https://img.shields.io/badge/twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/)

```
   puts "Hello World"
```

</details>

