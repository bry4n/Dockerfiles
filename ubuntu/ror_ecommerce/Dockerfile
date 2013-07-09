FROM bry4n/ruby19

RUN gem install debugger

RUN git clone https://github.com/drhenner/ror_ecommerce.git webapp
RUN cd webapp && cp config/database.yml.sql_ite3 config/database.yml
RUN cd webapp && bundle install
RUN touch webapp/config/settings.yml
RUN cd webapp && rake db:migrate
RUN cd webapp && rake db:seed 
RUN cd webapp && rake db:seed_fake 

ADD ./bootstrap.sh ./bootstrap.sh

RUN chmod +x ./bootstrap.sh

EXPOSE 3000
CMD ["./bootstrap.sh"]
