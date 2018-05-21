FROM scratch
ADD rootfs.tar.xz /
ENV LD_LIBRARY_PATH /usr/lib:/lib:.

# Update repository info ;\# Install some base packages that we will need later on.
RUN apk update ;\
apk upgrade ;\
apk --no-cache add ca-certificates wget curl unzip libgcc;\
wget -q -O /etc/apk/keys/sgerrand.rsa.pub https://raw.githubusercontent.com/sgerrand/alpine-pkg-glibc/master/sgerrand.rsa.pub ;\
wget https://github.com/sgerrand/alpine-pkg-glibc/releases/download/2.27-r0/glibc-2.27-r0.apk ;\
apk add glibc-2.27-r0.apk ;\
rm -rf glibc-2.27-r0.apk

CMD ["/bin/sh"]
