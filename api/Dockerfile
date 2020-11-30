FROM ruby:3.0-rc-alpine

RUN apk update && apk --no-cache --update add \
        build-base \
        tzdata

WORKDIR /app

COPY *Gemfile* ./
RUN bundle install

ENV \
        BINDING=0.0.0.0 \
        PORT=3000 \
        RAILS_ENV=development

CMD ["bundle", "exec", "rails", "server"]