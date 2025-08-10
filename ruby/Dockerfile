FROM ruby:3.3.5

WORKDIR /app

RUN gem install sinatra -v 4.1.1
RUN gem install rackup -v 2.2.1
RUN gem install puma -v 6.6

COPY . .

CMD ["ruby", "app.rb"]