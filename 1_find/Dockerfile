FROM ruby:3.1.2

RUN apt-get update && apt-get install -y curl apt-transport-https wget sqlite3 build-essential libsqlite3-dev && \
wget --quiet -O - /tmp/pubkey.gpg https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - && \
echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list && \
apt-get update && apt-get install -y yarn

RUN curl -fsSL https://deb.nodesource.com/setup_16.x | bash - && apt-get install -y nodejs

WORKDIR /myapp
COPY . /myapp

RUN bundle install


