#all in one install
#RUN apt-get update -y && apt-get install -y build-essential libpq-dev nodejs
#if rakefile
#ONBUILD RUN rake db:migrate && \
#	rake db:setup && \
#	rake db:seed
FROM ruby:2.3

RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install -y sqlite3
RUN gem install rails

ONBUILD COPY . /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD RUN gem install bundler rails && bundle install
ONBUILD EXPOSE 3000
