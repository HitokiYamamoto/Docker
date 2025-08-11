FROM ruby:3.2.2

RUN apt-get update -qq && apt-get install -y \
    build-essential \
    libpq-dev \
    nodejs \
    yarn \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app

RUN gem install rails -v 8.0.2
