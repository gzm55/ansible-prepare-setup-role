From danielguerra/alpine-sshd

ENV GLIBC_VERSION 2.29-r0

# Download and install glibc
RUN set -ex && \
  apk add --update curl sudo && \
  curl -Lo /etc/apk/keys/sgerrand.rsa.pub https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub && \
  curl -Lo glibc.apk "https://github.com/sgerrand/alpine-pkg-glibc/releases/download/${GLIBC_VERSION}/glibc-${GLIBC_VERSION}.apk" && \
  curl -Lo glibc-bin.apk "https://github.com/sgerrand/alpine-pkg-glibc/releases/download/${GLIBC_VERSION}/glibc-bin-${GLIBC_VERSION}.apk" && \
  apk add glibc-bin.apk glibc.apk && \
  /usr/glibc-compat/sbin/ldconfig /lib /usr/glibc-compat/lib && \
  echo 'hosts: files mdns4_minimal [NOTFOUND=return] dns mdns4' >> /etc/nsswitch.conf && \
  echo -e "123456\n123456\n" | passwd && \
  echo -e "123456\n123456\n" | adduser userA && \
  echo "PermitRootLogin yes" >> /etc/ssh/sshd_config && \
  echo "Defaults !requiretty" >/etc/sudoers.d/reqtty && \
  addgroup userA wheel && \
  rm -rf glibc.apk glibc-bin.apk /var/cache/apk/*
