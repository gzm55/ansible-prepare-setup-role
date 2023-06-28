From hermsi/alpine-sshd

ENV ROOT_PASSWORD 123456
ENV ROOT_KEYPAIR_LOGIN_ENABLED true

# install packages and setup accounts
RUN set -ex && \
  apk add --update sudo && \
  echo "Defaults !requiretty" >/etc/sudoers.d/reqtty && \
  echo -e "123456\n123456\n" | adduser userA && \
  addgroup userA wheel
