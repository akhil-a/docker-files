# Set the base image to Ubuntu
FROM ubuntu

#Install some commands basic things
RUN apt-get update && apt-get install -y cloc tree git-core flex bison gperf build-essential zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 libxml2-utils unzip python-pip

#Install RSU Specific packages
RUN dpkg --add-architecture i386
RUN  apt-get update && apt-get install -y libc6:i386 libncurses5:i386 libstdc++6:i386  python-lxml

#Install Java JDK 8.0
RUN apt-get install -y openjdk-8-jdk
RUN apt-get install -y wget

#Download and create build environment
RUN wget https://launchpad.net/gcc-arm-embedded/4.9/4.9-2015-q3-update/+download/gcc-arm-none-eabi-4_9-2015q3-20150921-linux.tar.bz2

RUN mkdir RSU_SOURCE
RUN mkdir /home/brcm_tools
RUN chown $(whoami) -R /home/brcm_tools
RUN chgrp $(whoami) -R /home/brcm_tools
RUN mv gcc-arm-none-eabi-4_9-2015q3-20150921-linux.tar.bz2 /home/brcm_tools/
RUN cd /home/brcm_tools &&  tar -xf gcc-arm-none-eabi-4_9-2015q3-20150921-linux.tar.bz2
RUN  ssh-keygen -t rsa -f ~/.ssh/id_rsa -P ""
RUN cat ~/.ssh/id_rsa.pub
