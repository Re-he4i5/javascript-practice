FROM ruby:3.1.2

# ENV ROOT="rails-app"

RUN gem install rails -v 6.1.4

WORKDIR /usr/src
RUN curl -sL https://deb.nodesource.com/setup_16.x -o nodesource_setup.sh && bash nodesource_setup.sh && apt-get update && apt-get install nodejs

RUN npm install -g yarn

# WORKDIR ${ROOT}
# COPY Gemfile ${ROOT}
# COPY Gemfile.lock ${ROOT}

# COPY . ${ROOT}

RUN mkdir /app_name
ENV APP_ROOT /usr/src/app_name
WORKDIR ${APP_ROOT}

COPY . $APP_ROOT

RUN bundle install

EXPOSE 3000
CMD ["rails", "server", "-b", "0.0.0.0"]