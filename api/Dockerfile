FROM ruby:3.0-rc-alpine

RUN apk update && apk --no-cache --update add \
	build-base~=0.5 \
	postgresql-dev~=12.5 \
	tzdata~=2020

WORKDIR /app

COPY Gemfile Gemfile.lock ./
RUN bundle install

ENV \
	BINDING=0.0.0.0 \
	PORT=3000 \
	RAILS_ENV=development

CMD ["bundle", "exec", "rails", "server"]
