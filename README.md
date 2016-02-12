# Chessxpert  
## Server Setup Instructions (Linux server)
1. [Download Oracle JDK](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html "Download Oracle JDK")
2. Upload .gz file to /usr/local/java and change to that directory
3. Type "sudo tar xvzf jdk-8u65-linux-x64.gz"
4. sudo vi /etc/profile
5. Update the following, replacing jdk1.8.0_65 with the version you downloaded:  
	*JAVA_HOME=/usr/local/java/jdk1.8.0_65*  
	*JRE_HOME=$JAVA_HOME/jre*  
	*PATH=$PATH:$JAVA_HOME/bin:$JRE_HOME/bin*  
	*export JAVA_HOME*  
	*export JRE_HOME*  
	*export PATH* 
6. Type “. /etc/profile”
7. Type the following, replacing jdk1.8.0_65 with the version you downloaded:  
	*sudo update-alternatives --install "/usr/bin/java" "java"*  
    *"/usr/local/java/jdk1.8.0_65/bin/java" 1*  
    *sudo update-alternatives --install "/usr/bin/javac" "javac"*  
    *"/usr/local/java/jdk1.8.0_65/bin/javac" 1*  
    *sudo update-alternatives --install "/usr/bin/javaws" "javaws"*  
    *"/usr/local/java/jdk1.8.0_65/bin/javaws" 1*  
    *sudo update-alternatives --set java /usr/local/java/jdk1.8.0_65/bin/java*  
    *sudo update-alternatives --set javac /usr/local/java/jdk1.8.0_65/bin/javac*    
    *sudo update-alternatives --set javaws /usr/local/java/jdk1.8.0_65/bin/javaws*
8. Type “sudo apt-get install tomcat7”
9. Type “sudo apt-get install tomcat7-docs tomcat7-admin tomcat7-examples”
10. Ensure that your server configuration has open ports for SSH, HTTP, and custom 8080 port for TomCat  

## How to update project on your server  
1. Open project in eclipse
2. Export in the Web option as .WAR file
3. Use SCP to upload as root.
4. Move .WAR file to /var/lib/tomcat7/webapps  

## How to test project
Access http://yourdomain.com:8080/chess/MyServlet from inside your web browser.  
For example, [http://chessxpert.com:8080/chess/MyServlet](http://chessxpert.com:8080/chess/MyServlet)
