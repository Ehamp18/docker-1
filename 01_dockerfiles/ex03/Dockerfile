FROM debian

RUN apt-get update && apt-get install -y curl openssh-server ca-certificates postfix

RUN curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | /bin/bash

RUN apt-get install -y gitlab-ce

EXPOSE 443 80 22

ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && /bin/bash
