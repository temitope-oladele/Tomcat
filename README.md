# Tomcat
This contains Tomcat Installation and Configuration on Linux RedHart Server

# Step 1: Pre-requisites of the installation
#1 EC2 Instance: Create RedHart Server on AWS with minimum of t2-micro. Tomcat is light weight and it can take that.
#2 Apache Tomcat requires Java to be install:
     .. $ sudo yum install java-1.8.0-openjdk-devel -y
 Confirm Java has been installed with:
     ..$ java -version
 # Step 2: Tomcat Installation
 
 sudo yum install wget zip unzip -y
 
 #Download Tomcat packages to your working home directory and in this case, it opt that we use in our environment
 
cd /opt

sudo wget  https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.73/bin/apache-tomcat-9.0.73.zip 

#Extract the zipped directory, remove it and rename the extracted tomcat directory

sudo unzip apache-tomcat-9.0.73.zip 

sudo rm -rf apache-tomcat-9.0.73.zip 

sudo mv apache-tomcat-9.0.73 tomcat9

# Step 3: Give executing permissions to tocat9 to allow catalina.sh, startup.sh and shutdown.sh and many more important functions to work or you can give the permission singly.

chmod +x /opt/tomcat9

#or if you want to give a full permission you can execute:

chmod 777 -R /opt/tomcat9

#it is important to create a link to manage up and down of the tomcat server. This will note work if the right permission is not given to catalina.sh in the bin directory.
sudo ln -s /opt/tomcat9/bin/startup.sh /usr/local/bin/tomcatup
ln -s /opt/tomcat9/bin/shutdown.sh /usr/local/bin/tomcatdown

# Step 4: Start Tomcat
#Start Tomcat as below provided you established the link creation else run the second to start Tomcat since bin directory has the right permission.

tomcatup

or

sh /opt/tomcat9/bin/startup.sh

#The  Tomcat at this point has been fully configured. The default port for Tomcat is 8080 which is the same as Jenkins therefore you may decide to change port here to something else within permissible range something like 8090 and this can be done using the /conf/server.xml 

use the sudo find / -name <file_name>    to find the ansolute path of the server.xml

sudo find / -name server.xml

   <Connector port="8090" protocol="HTTP/1.1"
               connectionTimeout="20000"
               redirectPort="8443" />


sudo vi /opt/tomcat9/conf/server.xml

#comment the value ClassName field in context file to allow external access to operate Tomcat gui

sudo vi /opt/tomcat9/webapps/manager/META-INF/context.xml

<!--
  <Valve className="org.apache.catalina.valves.RemoteAddrValve"
         allow="127\.\d+\.\d+\.\d+|::1|0:0:0:0:0:0:0:1" /> -->

# Step 5: Configure Users
#The last straw on this is to update users information from tomcat-users.xml
sudo vi /opt/tomcat9/conf/tomcat-users.xml


An example is of user setup is below:

<role rolename="manager-gui"/>
 <role rolename="manager-script"/>
 <role rolename="manager-jmx"/>
 <role rolename="manager-status"/>
 <user username="admin" password="admin123" roles="manager-gui, manager-script, manager-jmx, manager-status"/>
 <user username="Manager1" password="manager123" roles="manager-gui, manager-script"/>
 <user username="tomcat" password="s3cret" roles="manager-gui"/>

# Step 6: Run Tomcat on GUI is you 
#Restart serivce [you may run tomcatdown and then tomcatup] then login to tomcat application from your browser [http://ip_address:port_Number] and then to the Manager GUI. Ensure you open the assigned Tomcat port in the AWS Tomcat server then you are good to go.

Tomcat should be up and running
