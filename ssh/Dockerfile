FROM ubuntu:16.04
MAINTAINER Xiao Mo

COPY sources.list /etc/apt/sources.list

RUN apt-get update \
    && apt-get install -y openssh-server \
    && mkdir /var/run/sshd \
    && echo 'root:root' | chpasswd \
    && sed -ri 's/^PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config \
    && sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config \
    && apt-get clean all

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]