FROM ruby:2.6.6-slim-buster

RUN apt-get update && \
      apt-get install -y -qq build-essential unzip curl

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && \
  unzip awscliv2.zip && \
  ./aws/install

COPY Gemfile .
RUN gem install bundler && bundle install -j `nproc --all`

CMD bash
