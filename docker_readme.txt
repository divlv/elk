#
#  _  _      _____ ____     _____            __  __   _ 
# | || |    / ____|  _ \   |  __ \     /\   |  \/  | | |
# | || |_  | |  __| |_) |  | |__) |   /  \  | \  / | | |
# |__   _| | | |_ |  _ <   |  _  /   / /\ \ | |\/| | | |
#    | |   | |__| | |_) |  | | \ \  / ____ \| |  | | |_|
#    |_|    \_____|____/   |_|  \_\/_/    \_\_|  |_| (_)
#
# Docker commands
#
# Pull the Docker Image:
docker pull sebp/elk
#
# Start the ELK stack:
************************************************************************************
docker run -d -p 80:5601 -p 9200:9200 -p 9300:9300 -p 12201:12201/udp wfelk
************************************************************************************

# And stop all containers, based on "wfelk"
------------------------------------------------------------------------------------
docker stop $(docker ps -q --filter ancestor=wfelk)
------------------------------------------------------------------------------------


# Delete every Docker containers
# Must be run first because images are attached to containers
docker rm -f $(docker ps -a -q)

# Delete every Docker image
docker rmi -f $(docker images -q)

#####################################
stop all containers:
docker kill $(docker ps -q)

remove all containers
docker rm $(docker ps -a -q)

remove all docker images
docker rmi $(docker images -q)

#####################################
# Remove unused data
docker system prune --all
