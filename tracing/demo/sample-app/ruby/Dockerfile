FROM ruby:3.4.1-slim

RUN apt-get update -qq && apt-get install -y build-essential libpq-dev

WORKDIR /app

COPY Gemfile Gemfile.lock ./

RUN bundle install

COPY . .

CMD ["bin/rails", "server", "-p", "3000", "-b", "0.0.0.0"]
