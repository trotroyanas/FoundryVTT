FROM ubuntu:latest

# Build-arg: User ID for the created foundry user
ENV UID=1026
# Build-arg: Group ID for the created group
ENV GUID=65534
# Set the foundry install home
ENV FOUNDRY_HOME=/home/foundry/fvtt

RUN mkdir -p /home/foundry/fvtt

RUN echo "UID ${UID}"
# add a foundry group with a guid listed above

RUN echo "UID: ${UID} GUID: $GUID"
# create the foundry use
RUN adduser -u $UID -h "$FOUNDRY_HOME" -D foundry

# Set the current working directory
WORKDIR "${FOUNDRY_HOME}"


# installing unzip and bash shell
RUN apt-get update

#curl nginx unzip
RUN apt-get install curl -y
RUN curl -sL https://deb.nodesource.com/setup_10.x  | bash -
RUN apt-get -y install nodejs
RUN apt-get -y install nginx unzip

#nginx pararm 
RUN rm /etc/nginx/sites-enabled/default
RUN service nginx restart
#Pm2
RUN npm install pm2 -g

#copy found
COPY ./foundryvtt*.zip .

#unzip 
RUN unzip foundryvtt*.zip
RUN rm foundryvtt*.zip
#pm2
#RUN pm2 startup
#RUN pm2 start "${FOUNDRY_HOME}/resources/app/main.js" --name "foundry" -- --port=30000
#RUN pm2 save

EXPOSE 30000
CMD [ "node", "resources/app/main.js" ]