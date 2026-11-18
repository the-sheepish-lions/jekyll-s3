ARG TARGETPLATFORM=linux/amd64
FROM ruby:2.7.8-slim-buster

RUN cat <<EOF > /etc/apt/sources.list
deb http://archive.debian.org/debian/ buster main contrib non-free
deb http://archive.debian.org/debian/ buster-proposed-updates main contrib non-free
deb http://archive.debian.org/debian-security buster/updates main contrib non-free
EOF

RUN apt-get update && apt-get install -y -qq build-essential unzip curl

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && \
  unzip awscliv2.zip && \
  ./aws/install

COPY Gemfile .
RUN gem install bundler -v 2.4.22 && bundle install -j `nproc --all`

CMD ["bash"]
