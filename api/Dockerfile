FROM ruby:2.5.7

RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs

WORKDIR /rails-app

COPY Gemfile .
COPY Gemfile.lock .

RUN bundle install

COPY . .

CMD ["rails", "server", "-b", "0.0.0.0"]