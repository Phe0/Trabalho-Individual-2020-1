FROM ruby:2.5.7

RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs

RUN mkdir /rails-app

WORKDIR /rails-app

ADD Gemfile /rails-app
ADD Gemfile.lock /rails-app

RUN bundle install

ADD . /rails-app

CMD ["rails", "server", "-b", "0.0.0.0"]