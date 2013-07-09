FROM ubuntu

MAINTAINER Bryan Goines <me@bryangoines.com>

ENV RUBY_VERSION 2.0.0-p247

RUN apt-get -y update

RUN apt-get install -y wget curl git-core
RUN apt-get install -y ca-certificates
RUN apt-get install -y build-essential make g++
RUN apt-get install -y zlib1g-dev libssl-dev libxml2-dev libxslt-dev libreadline6-dev libyaml-dev
RUN apt-get install -y sqlite3 libsqlite3-dev

RUN wget http://ftp.ruby-lang.org/pub/ruby/2.0/ruby-$RUBY_VERSION.tar.gz
RUN tar -xzvf ruby-$RUBY_VERSION.tar.gz
RUN cd ruby-$RUBY_VERSION && ./configure --prefix=/usr/local
RUN cd ruby-$RUBY_VERSION && make && make install

RUN gem install bundler
