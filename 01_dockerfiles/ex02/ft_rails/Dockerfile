FROM ruby:latest

RUN apt-get update && apt-get upgrade -y nodejs
RUN gem install rails && gem install bundler
RUN gem install nodejs-rails && gem update --system

ONBUILD WORKDIR /opt
ONBUILD ADD app /opt/app
ONBUILD WORKDIR /opt/app
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

ONBUILD EXPOSE 3000
