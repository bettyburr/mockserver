#
# MockServer Dockerfile
#
# https://github.com/jamesdbloom/mockserver
# http://www.mock-server.com
#

# pull base image
FROM java

# maintainer details
MAINTAINER James Bloom "jamesdbloom@gmail.com"

# set working directory
RUN mkdir -p /opt/mockserver
WORKDIR /opt/mockserver

# download MockServer
RUN  \
  cd /opt/mockserver && \
  wget -O mockserver-netty-jar-with-dependencies.jar https://oss.sonatype.org/content/repositories/releases/org/mock-server/mockserver-netty/3.9.17/mockserver-netty-3.9.17-jar-with-dependencies.jar && \
  wget https://raw.github.com/jamesdbloom/mockserver/master/docker/run_mockserver.sh && \
  chmod +x /opt/mockserver/run_mockserver.sh

# expose ports.
EXPOSE 1080 1090

# define default command.
CMD ["/opt/mockserver/run_mockserver.sh", "-logLevel", "INFO", "-serverPort", "1080", "-proxyPort", "1090"]
