FROM bry4n/ruby19

ENV USERNAME admin
ENV PASSWORD password
ENV EMAIL admin@example.com

RUN gem install debugger

RUN apt-get install -y libpq-dev

RUN git clone https://github.com/fatfreecrm/fat_free_crm.git ffcrm
RUN cd ffcrm && cp config/database.sqlite.yml config/database.yml
RUN cd ffcrm && bundle install --without heroku
RUN touch ffcrm/config/settings.yml
RUN cd ffcrm && rake db:migrate
RUN cd ffcrm && rake ffcrm:setup:admin

ADD ./bootstrap.sh ./bootstrap.sh

RUN chmod +x ./bootstrap.sh

EXPOSE 3000
CMD ["./bootstrap.sh"]
