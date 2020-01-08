# Set the base image to Ubuntu
FROM ubuntu

#Install some commands like cloc and tree
RUN apt-get update && apt-get install -y cloc tree git-core gnupg flex bison gperf build-essential zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 lib32ncurses5-dev x11proto-core-dev libx11-dev lib32z-dev ccache libgl1-mesa-dev libxml2-utils xsltproc unzip libssl-dev dos2unix

RUN apt-get install -y openjdk-8-jdk

RUN mkdir RSE_SOURCE
#CMD ["--add-host=bitbucket-pais.eu.panasonic.com:10.100.238.150"]

RUN echo 10.100.238.139       bamboo-pais.eu.panasonic.com >> /etc/hosts; cat /etc/hosts
