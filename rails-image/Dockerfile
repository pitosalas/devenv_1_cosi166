FROM ruby:latest

# Upgrade RubyGems and install the latest Bundler version
RUN gem update --system && \
    gem install bundler && \
    gem install rails

RUN apt-get update && apt-get install -y \
    build-essential \
    micro \
    postgresql-client \
    libxml2-dev \
    libxslt-dev

RUN mkdir -p /app
WORKDIR /app
COPY . /app/
RUN gem install rails
RUN pwd && ls

# Document that we're going to expose port 3000
EXPOSE 3000
ENTRYPOINT ["tail", "-f", "/dev/null"]