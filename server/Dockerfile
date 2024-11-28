FROM ubuntu

LABEL maintainer="ahmed@gmail.com"   

EXPOSE 22

WORKDIR /root

RUN apt update -y && \
    apt install openssh-server -y  && \
    echo "PermitRootLogin yes" >>  /etc/ssh/sshd_config && \
    mkdir -p /run/sshd && \
    echo "root:0" | chpasswd && \
    # Clean up apt cache to reduce image size
    rm -rf /var/lib/apt/lists/*

    CMD ["/usr/sbin/sshd", "-D"]
