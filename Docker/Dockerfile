FROM alpine:3.13

# Set the foundry install home
RUN adduser -D foundry
RUN mkdir -p /home/foundry/fvtt
RUN mkdir -p /home/foundry/fvttdata


ENV FOUNDRY_HOME=/home/foundry/fvtt
ENV FOUNDRY_DATA=/home/foundry/fvttdata


RUN apk add --update nodejs=14.16.1-r1

# Set the current working directory
WORKDIR "${FOUNDRY_HOME}"

#copy found
COPY ./foundryvtt-0.8.5.zip .

#unzip
RUN unzip foundryvtt*.zip
RUN rm foundryvtt*.zip

EXPOSE 30000
#CMD [ "node", "resources/app/main.js" ]
CMD node ${FOUNDRY_HOME}/resources/app/main.js --dataPath=${FOUNDRY_DATA}
