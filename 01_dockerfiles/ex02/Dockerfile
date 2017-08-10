FROM ruby

RUN apt-get update -y && apt-get upgrade -y
RUN gem install rails
RUN apt-get install nodejs -y
RUN apt-get install build-essential -y

EXPOSE 3000

ONBUILD COPY . /opt/app

ONBUILD WORKERDIR /opt/app

#ONBUILD COPY Gemfile Gemfile.lock ./
#ONBUILD RUN gem install bundler && bundle install 

#ONBUILD COPY . ./

ONBUILD RUN bundle install
ONBUILD RUN rails db:migrate
ONBUILD RUN rails db:seed


#ONBUILD CMD ["bundle", "exec", "rails", "server,", "-b", "0.0.0.0"]

