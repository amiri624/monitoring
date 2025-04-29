


### monitoring
## 1: install Docker
```bash
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```
### and 
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
## 2: grafana docker compose
### docker-compose.yml
#### RAW
```bash
https://raw.githubusercontent.com/amiri624/monitoring/refs/heads/main/docker-compose.yml
```
### 3: *Important
```bash
docker pull prom/prometheus:latest
```
```bash
docker pull grafana/grafana:latest
```
### Copy Dockerfile from viscod on Srerver (we need srv ip)
```bash
scp monitoring/docker-compose.yml meisam@192.168.122.65
```
## 4:

```bash
docker compose up -d
```
