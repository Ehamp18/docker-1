FROM ruby:latest

RUN apt-get update && apt-get upgrade -y nodejs sqlite3 gem
RUN gem install bundler:1.16.1
RUN gem install rails && gem update rails
RUN gem install rails bundle rake

ONBUILD WORKDIR /opt
ONBUILD ADD app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD RUN bundle install
ONBUILD RUN bundle update rails
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

ONBUILD EXPOSE 3000
