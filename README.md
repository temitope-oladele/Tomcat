# Tomcat
This contains Tomcat Installation and Configuration on Linux RedHat Server

### Step 1: Pre-requisites of the installation
* 1 EC2 Instance: Create RedHat Server on AWS with minimum of t2-micro. Tomcat is light weight and it can take that.
* 2 Apache Tomcat requires Java to be install:
<div>
  <pre><code>sudo yum install java-1.8.0-openjdk-devel -y</code></pre>
  <button onclick="navigator.clipboard.writeText('sudo yum install java-1.8.0-openjdk-devel -y')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>
    
 Confirm Java has been installed with:
 <div>
  <pre><code>java -version</code></pre>
  <button onclick="navigator.clipboard.writeText('java -version')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>
 
 ### Step 2: Tomcat Installation
 
  <div>
  <pre><code>sudo yum install wget zip unzip -y</code></pre>
  <button onclick="navigator.clipboard.writeText('sudo yum install wget zip unzip -y')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

 
Download Tomcat packages to your working home directory and in this case, it opt that we use in our environment

  <div>
  <pre><code>cd /opt</code></pre>
  <button onclick="navigator.clipboard.writeText('cd /opt')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

 <div>
  <pre><code>sudo wget  https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.73/bin/apache-tomcat-9.0.73.zip</code></pre>
  <button onclick="navigator.clipboard.writeText('sudo wget  https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.73/bin/apache-tomcat-9.0.73.zip ')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

Extract the zipped directory, remove it and rename the extracted tomcat directory

 <div>
  <pre><code>sudo unzip apache-tomcat-9.0.73.zip</code></pre>
  <button onclick="navigator.clipboard.writeText('sudo unzip apache-tomcat-9.0.73.zip')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

 <div>
  <pre><code>sudo rm -rf apache-tomcat-9.0.73.zip </code></pre>
  <button onclick="navigator.clipboard.writeText('sudo rm -rf apache-tomcat-9.0.73.zip ')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

 <div>
  <pre><code>sudo mv apache-tomcat-9.0.73 tomcat9</code></pre>
  <button onclick="navigator.clipboard.writeText('sudo mv apache-tomcat-9.0.73 tomcat9')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

### Step 3: Give executing permissions to tomcat
This is to allow catalina.sh, startup.sh and shutdown.sh and many more important functions to work or you can give the permission singly.

<div>
  <pre><code>chmod +x /opt/tomcat9</code></pre>
  <button onclick="navigator.clipboard.writeText('chmod +x /opt/tomcat9')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

...or if you want to give a full permission you can execute:

<div>
  <pre><code>chmod 777 -R /opt/tomcat9</code></pre>
  <button onclick="navigator.clipboard.writeText('chmod 777 -R /opt/tomcat9')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

It is important to create a link to manage up and down of the tomcat server. This will note work if the right permission is not given to catalina.sh in the bin directory.

<div>
  <pre><code>sudo ln -s /opt/tomcat9/bin/startup.sh /usr/local/bin/tomcatup</code></pre>
  <button onclick="navigator.clipboard.writeText('sudo ln -s /opt/tomcat9/bin/startup.sh /usr/local/bin/tomcatup')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

<div>
  <pre><code>ln -s /opt/tomcat9/bin/shutdown.sh /usr/local/bin/tomcatdown</code></pre>
  <button onclick="navigator.clipboard.writeText('ln -s /opt/tomcat9/bin/shutdown.sh /usr/local/bin/tomcatdown')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

### Step 4: Start Tomcat
Start Tomcat as below provided you established the link creation else run the second to start Tomcat since bin directory has the right permission.
<div>
  <pre><code>tomcatup</code></pre>
  <button onclick="navigator.clipboard.writeText('tomcatup')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

or

<div>
  <pre><code>sh /opt/tomcat9/bin/startup.sh</code></pre>
  <button onclick="navigator.clipboard.writeText('sh /opt/tomcat9/bin/startup.sh')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>


The  Tomcat at this point has been fully configured. The default port for Tomcat is 8080 which is the same as Jenkins therefore you may decide to change port here to something else within permissible range something like 8090 and this can be done using the /conf/server.xml 

use the sudo find / -name <file_name>    to find the ansolute path of the server.xml

<div>
  <pre><code>sudo find / -name server.xml</code></pre>
  <button onclick="navigator.clipboard.writeText('sudo find / -name server.xml')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

   <Connector port="8090" protocol="HTTP/1.1"
               connectionTimeout="20000"
               redirectPort="8443" />

<div>
  <pre><code>sudo vi /opt/tomcat9/conf/server.xml</code></pre>
  <button onclick="navigator.clipboard.writeText('sudo vi /opt/tomcat9/conf/server.xml')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

comment the value ClassName field in context file to allow external access to operate Tomcat gui

<div>
  <pre><code>sudo vi /opt/tomcat9/webapps/manager/META-INF/context.xml</code></pre>
  <button onclick="navigator.clipboard.writeText('sudo vi /opt/tomcat9/webapps/manager/META-INF/context.xml')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

"
<!--
  <Valve className="org.apache.catalina.valves.RemoteAddrValve"
         allow="127\.\d+\.\d+\.\d+|::1|0:0:0:0:0:0:0:1" /> -->
"
### Step 5: Configure Users
- The last straw on this is to update users information from tomcat-users.xml

<div>
  <pre><code>sudo vi /opt/tomcat9/conf/tomcat-users.xml</code></pre>
  <button onclick="navigator.clipboard.writeText('sudo vi /opt/tomcat9/conf/tomcat-users.xml')">
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h8v8H4zM12 4h8v8h-8zM4 12h8v8H4zM12 12h8v8h-8z"/></svg>
  </button>
</div>

An example is of user setup is below:

<role rolename="manager-gui"/>
 <role rolename="manager-script"/>
 <role rolename="manager-jmx"/>
 <role rolename="manager-status"/>
 <user username="admin" password="admin123" roles="manager-gui, manager-script, manager-jmx, manager-status"/>
 <user username="Manager1" password="manager123" roles="manager-gui, manager-script"/>
 <user username="tomcat" password="s3cret" roles="manager-gui"/>

### Step 6: Run Tomcat on GUI is you 
#Restart serivce [you may run tomcatdown and then tomcatup] then login to tomcat application from your browser [http://ip_address:port_Number] and then to the Manager GUI. Ensure you open the assigned Tomcat port in the AWS Tomcat server then you are good to go.

Tomcat should be up and running
