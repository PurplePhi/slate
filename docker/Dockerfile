FROM docker-registry.booking.com/jenkins-built/centos-7:latest
MAINTAINER "BookingSuite"

ENV http_proxy http://webproxy:3128/
ENV HTTP_PROXY http://webproxy:3128/
ENV https_proxy http://webproxy:3128/
ENV HTTPS_PROXY http://webproxy:3128/
ENV RSYNC_PROXY http://webproxy:3128/

EXPOSE 80

WORKDIR /root

RUN yum install -y nginx \
                   wget \
                   gcc-c++ \
		   make \
                   git \
                   bzip2

# Install nodejs
RUN curl --silent --location https://rpm.nodesource.com/setup_6.x | bash -
RUN sed -i -e 's$proxy=_none_$proxy=http://webproxy:3128/$g' /etc/yum.conf
RUN yum install -y nodejs

# Install ruby
RUN wget -O ruby-install-0.6.0.tar.gz https://github.com/postmodern/ruby-install/archive/v0.6.0.tar.gz
RUN tar -xzf ruby-install-0.6.0.tar.gz
RUN cd ruby-install-0.6.0/ && make install
RUN ruby-install -j8 --system ruby 2.2 -- --disable-install-rdoc
RUN gem update --system 2.6.1
RUN gem install --no-ri --no-rdoc bundler
RUN ln -s /usr/local/bin/bundle /usr/bin/

RUN mkdir -p /root/lib /root/source
COPY Gemfile Gemfile.lock config.rb font-selection.json ./
COPY lib/ ./lib/
COPY source/ ./source/
RUN bundle config build.nokogiri --use-system-libraries
RUN bundle install
RUN bundle exec middleman build --clean
RUN mv -f build/* /usr/share/nginx/

ADD ./nginx.conf /etc/nginx.conf

CMD ["/usr/sbin/nginx", "-c", "/etc/nginx.conf"]
