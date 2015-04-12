# This is a Dockerfile presents a sample contained application that does not use root privileges
#
# VERSION 0.1

FROM ubuntu

MAINTAINER Pasonaru Technologies, contact@pasonaru.com

# Add a group [servicegroup] and a user [user1]
RUN groupadd -r servicegroup  && useradd -r -g servicegroup user1

# Create a mount point and change its permissions
RUN mkdir -p /data/mountedfolder

# Mount a folder that requires user privilges 
# (note that this folder can only be used from other containers that also run as the specific user)
VOLUME  /data/mountedfolder
RUN chown -R user1 /data/mountedfolder

# Change the owner of an existing folder
RUN chown -R user1 tmp

# Switch to the low privilged user
USER user1



