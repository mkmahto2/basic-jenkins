# basic-jenkins
Connect to EC2 Instance using SSH
Installing Jenkins
.


Commands for Installing Jenkins on an EC2 instance
(Note: You can scroll to the right to see all the content in the box below.) We assume that your EC2 instance is running the 64-bit (x86) Ubuntu OS.
~~~
# Step 1 - Update existing packages
sudo apt-get update

# Step 2 - Install Java
sudo apt install -y default-jdk

# Step 3 - Download Jenkins package. 
# You can go to http://pkg.jenkins.io/debian/ to see the available commands
# First, add a key to your system
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -

# # Step 4 - Add the following entry in your /etc/apt/sources.list:
sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'

# # Step 5 -Update your local package index
sudo apt-get update

# Step 6 - Install Jenkins
sudo apt-get install -y jenkins

# Step 7 - Start the Jenkins server
sudo systemctl start jenkins

# Step 8 - Enable the service to load during boot
sudo systemctl enable jenkins
sudo systemctl status jenkins
~~~
# Logging into Jenkins using GUI


 Jenkins on an EC2 instance
(Note: You can scroll to the right to see all the content in the box below.) We assume that your EC2 instance is running the 64-bit (x86) Ubuntu OS.

# Step 1 - Update existing packages
sudo apt-get update

# Step 2 - Install Java
sudo apt install -y default-jdk

# Step 3 - Download Jenkins package. 
# You can go to http://pkg.jenkins.io/debian/ to see the available commands
# First, add a key to your system
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -

# # Step 4 - Add the following entry in your /etc/apt/sources.list:
sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'

# # Step 5 -Update your local package index
sudo apt-get update

# Step 6 - Install Jenkins
sudo apt-get install -y jenkins

# Step 7 - Start the Jenkins server
sudo systemctl start jenkins

# Step 8 - Enable the service to load during boot
sudo systemctl enable jenkins
sudo systemctl status jenkins
The sudo command allows us to run a command as root. The apt utility is for installing software. It is a package manager and performs dependency resolution to install the supporting libraries for the end user. A package manager facilitates easy installation, upgrading, and management of software on a computer. The -y option for apt enables it to automatically select the “yes” option to install the software and prevents prompting of the end user. You will observe in the step which adds “jenkins.list” that we are adding an additional software repository source for which our Linux computer will be able to install software from. This is referred to as an Apt Package Repo.

# Logging into Jenkins using GUI
Go to AWS dashboard to copy the public IP address of your Ubuntu EC2 instance.
Paste the public IP address into your browser, appended with ~~~ :8080 ~~~ port. For the first time, it will open up the Jenkins GUI as shown in the snapshot below:

Jenkins GUI saves the administrator password in a file on server

On the terminal, where you have connected to the Ubuntu EC2 instance, view the content of the file using the command sudo cat <path copied in the previous step>. It will show the default administrator password. You can copy and use this password in the GUI (browser) to log in first time.

After successful login, you may choose to install default plugins. Though, we will learn to use specific plugins for our needs in the next lesson. See the snapshot below.


If you choose to install suggested plugins, the following plugins would get installed. See the snapshot below:

Set up the user credentials. See the snapshot below:

Next, it will show you a success message and take you to the Jenkins dashboard.

# Enjoy
Jenkins dashboards
