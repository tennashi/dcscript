FROM golang:1.9.1-stretch

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y fish git neovim sudo

# create container user
RUN export uid=1000 gid=1000 && \
    echo "devyota:x:${uid}:${gid}:devyota,,,::/usr/bin/fish" >> /etc/passwd && \
    echo "devyota:x:${uid}:" >> /etc/group && \
    usermod -G sudo devyota && \
    echo 'devyota:devyota' | chpasswd

EXPOSE 4567

CMD [/usr/bin/fish]
