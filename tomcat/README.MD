# Usage
    #!/bin/bash
    docker run -it --privileged -d \
	 --restart always --name ksg \
	 -v /path/to/war:/usr/local/tomcat/webapps/ROOT \
	 -v /path/to/log/:/usr/local/tomcat/logs \
	 -p 8080:8080 daocloud.io/liushaoping/tomcat \
	 sh -c 'cd /usr/local/tomcat/webapps/ && ls | grep -v ROOT | xargs rm -rf && /usr/local/tomcat/bin/catalina.sh run'
    