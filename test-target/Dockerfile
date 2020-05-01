FROM ubuntu:18.04

WORKDIR /root

RUN apt update && apt install --yes openssh-server
RUN mkdir /var/run/sshd
RUN echo 'root:P@ssw0rd' | chpasswd
COPY ./test-target-key.pub /root/.ssh/authorized_keys
EXPOSE 22

# For Test.
RUN echo "this is test." > test.txt
RUN apt install --yes nginx
EXPOSE 80

CMD ["/usr/sbin/sshd", "-D"]

