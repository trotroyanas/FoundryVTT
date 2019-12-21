# FoundryVTT
# copy your foundryvtt-0.4.x.zip with other files docker-compose.xml...

#Build image
sudo docker-compose build

# Run the docker only container (for test)
sudo docker run --restart=always --name FoundryVTT.0.4.3 -p 30000:30000 -d fvtt:1.11.0


# Run the docker with volume map
sudo docker run --restart=always --name FoundryVTT.0.4.3 -p 30000:30000 -v /volume1/docker/foundry:/home/foundry -v /volume1/docker/foundry/FoundryVTT:/root/FoundryVTT  -d fvtt:1.11.0


