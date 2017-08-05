FROM debian:stretch

RUN apt-get update \
	&& apt-get install -y \
		ca-certificates \
		iptables

VOLUME /mnt/sysroot/inactive

RUN ln -sf rce-docker /usr/bin/docker \
	&& ln -sf rce-docker /usr/bin/dockerd \
	&& ln -sf rce-docker /usr/bin/docker-containerd \
	&& ln -sf rce-docker /usr/bin/docker-containerd-shim \
	&& ln -sf rce-docker /usr/bin/docker-containerd-ctr \
	&& ln -sf rce-docker /usr/bin/docker-runc \
	&& ln -sf rce-docker /usr/bin/docker-proxy

COPY rce-docker hostapp-update create /usr/bin/

CMD [ "/usr/bin/create" ]
