FROM debian:jessie

MAINTAINER Dimitri Justeau <dimitri.justeau@gmail.com>

# Inspired from docker examples (https://docs.docker.com/engine/examples/running_ssh_service/)
RUN apt-get update && apt-get install -y openssh-server
RUN mkdir /var/run/sshd
RUN echo 'root:sshdtoor' | chpasswd # IMPORTANT: Change password after creating a container!
RUN sed -i 's/PermitRootLogin without-password/PermitRootLogin yes/' /etc/ssh/sshd_config

# SSH login fix. Otherwise user is kicked off after login
RUN sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd

RUN echo "cd /home" >> /etc/profile

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
