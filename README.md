
# run jenkins in docker container

# run jenkins in docker container

# run jenkins in docker container
# Add dumy text
docker run --name jenkins-dind --privileged -d -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock jenkins/jenkins:lts
docker exec -u root -it c64e46542f80 sh
#Install Docker inside jenkins 

# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

apt install docker.io

sudo chown root:docker /var/run/docker.sock
sudo chmod 660 /var/run/docker.sock
usermod -aG docker jenkins

docker restart c64e46542f80

# Then run jenkins job with jenkins



