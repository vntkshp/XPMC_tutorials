# 💻 Azure Devops Video Tutorials
<details>

<summary><h3> 1. Create a Virtual Machine(VM)</h3></summary><br><br>
   * Configure VM with the same settings as in the Screenshots.<br>
   * Save User-Name and Password for later use<br>
   * Stop VM when not in use<br>
   * Delete VM when all tasks listed below are completed<br>
   * In Network Settings Create Inbound Rule for port 8080<br><br>

https://github.com/vntkshp/XPMC_tutorials/blob/2fa448e8c94fe485b29b264a126b42f01ee3ad6d/1_Virtual_Machine.mp4

<img src="https://github.com/vntkshp/XPMC_tutorials/blob/8a00e3ebbe300b48c2512d7e28529396476b3a51/Screenshorts/VM-Config.jpg" width="250"><br>
<img src="https://github.com/vntkshp/XPMC_tutorials/blob/8a00e3ebbe300b48c2512d7e28529396476b3a51/Screenshorts/VM-Disk.jpg" width="250"><br>
<img src="https://github.com/vntkshp/XPMC_tutorials/blob/92dd53cfcf413e17892e62bf5ce17d230a1b28f0/Screenshorts/VM-Network.jpg" width="250">


</details>



----------------------------------------------------------


<details>

<summary><h3>2. Create a DevOps Project in Organization</summary><br>
	* Create New Organisation and Project<br>
	* Give permissions to all members.<br>
</details>




----------------------------------------------------------



<details>

<summary><h3>3. Clone a project to Azure Repos
</summary><br>
	
   1. Clone [this](https://github.com/dockersamples/snake-game-tensorflow-docker.git) demo project from github to Repos<br>
   2. Create and Save **Personal Access Tokens** for later use<br>
   3. Create and Save **Git Credentials** for later use<br><br>
</details>



----------------------------------------------------------




<details>

<summary><h3>5. Run Docker on VM</summary><br>

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
```
sudo docker run hello-world
```

**Clone Repository to VM**
paste git repository link at the end for this to work

git clone <USERNAME>@<Public IP Address>


**Build image**
```
sudo docker build -t my-image .
```

**Run Docker Image**
```
sudo docker compose up -d
```

**Stop Docker Image**
```
sudo docker compose down
```

**List running docker containers**
```
sudo docker ps
```

</details>



----------------------------------------------------------




<details>

<summary><h3>6. Run app on nginx</summary>

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
sudo mv /etc/nginx/nginx.conf /etc/nginx/nginx.conf.bak
```


**Open nginx.conf**

```
sudo nano /etc/nginx/nginx.conf
```

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

<summary><h3>7. Create Pipeline
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

