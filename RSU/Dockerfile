# Set the base image to Ubuntu
FROM ubuntu

#Install RSU Specific packages
RUN dpkg --add-architecture i386
#Install some commands basic things
RUN apt-get update && apt-get install -y cloc tree git-core flex bison gperf build-essential zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 libxml2-utils unzip python-pip wget openjdk-8-jdk libc6:i386 libncurses5:i386 libstdc++6:i386  python-lxml

#Download and create build environment
RUN wget https://launchpad.net/gcc-arm-embedded/4.9/4.9-2015-q3-update/+download/gcc-arm-none-eabi-4_9-2015q3-20150921-linux.tar.bz2

RUN mkdir RSU_SOURCE
RUN mkdir /home/brcm_tools \
	&&  chown $(whoami) -R /home/brcm_tools \
	&& chgrp $(whoami) -R /home/brcm_tools \
	&& mv gcc-arm-none-eabi-4_9-2015q3-20150921-linux.tar.bz2 /home/brcm_tools/ && cd /home/brcm_tools \
	&&  tar -xf gcc-arm-none-eabi-4_9-2015q3-20150921-linux.tar.bz2
RUN  ssh-keygen -t rsa -f ~/.ssh/id_rsa -P "" && cat ~/.ssh/id_rsa.pub
COPY ./host_file.txt /usr/host_file.txt
RUN cat /usr/host_file.txt >> /etc/hosts

