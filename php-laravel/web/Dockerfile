FROM php:7

# 認証
RUN mkdir -m700 /root/.ssh
#COPY id_rsa /root/.ssh/
#RUN chmod 600 /root/.ssh/id_rsa
RUN ssh-keyscan -t rsa bitbucket.org >> ~/.ssh/known_hosts
RUN ssh-keyscan -t rsa github.com >> ~/.ssh/known_hosts

# apache
COPY zzz.conf /etc/httpd/conf.d/

# apache起動
CMD /usr/sbin/httpd -D FOREGROUND
