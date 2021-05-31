# FoundryVTT
# copy your foundryvtt-0.8.5.zip with other files docker-compose.xml...

#Build image
sudo docker-compose build

# Run the docker only container (for test)
sudo docker run --restart=unless-stopped --name Fvtt -p 30000:30000 -d fvtt:3.0


# Run the docker with volume map
sudo docker run \
--restart=unless-stopped \
--name Fvtt \
-p 30000:30000 \
-v /data/your/folder/app:/home/foundry/fvttd \
-v /data/your/folder/data:/home/foundry/fvttdata \
-d fvtt:3.0


