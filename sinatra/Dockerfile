# # 1. ubuntu 설치 (패키지 업데이트 + 만든사람 표시)
# FROM ubuntu:22.04
# RUN apt-get update -y -qq && apt-get install -y -qq ruby

# # 2. ruby 설치
# RUN apt-get install -y ruby
# RUN gem install bundler

# Refactoring
FROM ruby:latest
LABEL maintainer="koolerjaebee@gmail.com"

RUN gem install rackup

# 3. 소스 복사
# COPY . /usr/src/app
COPY Gemfile* /usr/src/app/

# 4. Gem 패키지 설치 (실행 디렉토리 설정)
WORKDIR /usr/src/app
RUN bundle install
COPY . /usr/src/app/
RUN bundle add rackup

# 5. Sinatra 서버 실행 (Listen 포트 정의)
EXPOSE 4567
CMD bundle exec ruby app.rb -o 0.0.0.0


