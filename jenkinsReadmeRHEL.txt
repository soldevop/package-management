sudo hostname ci
sudo yum -y install unzip wget tree git
sudo wget -c --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u131-b11/d54c1d3a095b4ff2b6607d096fa80163/jdk-8u131-linux-x64.rpm
sudo yum install jdk-8u131-linux-x64.rpm -y
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
cd /etc/yum.repos.d/
sudo curl -O https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo yum -y install jenkins  --nobest
sudo systemctl start jenkins
sudo systemctl enable jenkins
sudo systemctl status jenkins
curl ifconfig.co  # To get the IP of the server and use it to open it in the brwoser with the port 8080
sudo cat /var/lib/jenkins/secrets/initialAdminPassword  # to get the initial admin password needed for the GUi configuration
