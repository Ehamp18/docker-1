FROM Debian:latest

MAINTAINER elhampto <elhampto@student.42.us.org>

RUN apt-get update && apt-get upgrade -y && \
	apt-get install -y ca-certificates openssh-server wget postfix
RUN curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | /bin/bash

RUN apt-get install -y gitlab-ce
EXPOSE 443 80 22

ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && tail -f /dev/null