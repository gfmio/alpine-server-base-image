FROM alpine:3.2
COPY scripts/mkimage-alpine.bash scripts/apk-install /
RUN /apk-install bash tzdata
RUN apk update
RUN apk upgrade
RUN setup-sshd -c openssh; exit 0
RUN rc-update add hostname boot
RUN rc-update add networking boot
RUN rc-update add urandom boot
RUN rc-update add crond
RUN rc-update add swap boot
RUN rc-update add sshd boot
ENTRYPOINT ["/mkimage-alpine.bash"]
