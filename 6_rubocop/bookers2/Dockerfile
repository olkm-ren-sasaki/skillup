FROM ruby:2.6.3

# パッケージのインストール
RUN apt-get update -qq \
&& apt-get install -y nodejs npm \
&& rm -rf /var/lib/apt/lists/* \
&& npm install --global yarn

# 作業ディレクトリの指定
WORKDIR /myapp
COPY Gemfile /myapp/Gemfile
COPY Gemfile.lock /myapp/Gemfile.lock
COPY . /myapp
RUN bundle install \
&& rails db:migrate \
&& yarn install
