FROM debian

RUN apt-get update -y && \
	apt-get install -y curl openssh-server ca-certificates && \
	apt-get install -y postfix

RUN curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ee/script.deb.sh | bash
RUN EXTERNAL_URL="http://gitlab.example.com" apt-get install gitlab-ee
EXPOSE 22 80
ADD https://raw.githubusercontent.com/Wantiklo/Docker-1/master/01_dockerfiles/ex03/entrypoint.sh /entrypoint.sh
RUN chmod 777 /entrypoint.sh
CMD [ "bash", "/entrypoint.sh" ]

#docker run -it --rm -p 80:80 -p 22:22 -p --privileged rizkyario/42-docker-1-ex03
