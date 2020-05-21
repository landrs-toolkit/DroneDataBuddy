# DroneDataBuddy (2DB)
On board service to annotate, archive, and publish data as linked data onboard a companion computer

**Status:** Under development, beta not yet released
## How to use this repo
This repo contains the source for [DroneDataBuddy](./DroneDataBuddy/README.md) which includes information on how to deploy it on your drone.  Go straight here if you wish to deploy 2DB on a drone.

In addition, this repo currently also holds multiple submodules so as to enable a user or developer to try out 2DB locally on an x86 machine and with access to a drone, sensors, or companionion computer.  Specifically:
* [DockerPi](./DockerPi) is a fork of [https://github.com/lukechilds/dockerpi](https://github.com/lukechilds/dockerpi) allowing emulation of a Raspberry Pi companion computer 
* [DockerArdupilotSITL](./DockerArdupilotSITL) is  a fork of []().  SITL is the standard drone simulator for the Ardupilot autopilot.  This provides a means of simulating the outputs from a drone to demonstrate 2DB captureing flight data.

## What's in this repo

## Developer Use:
```
cd DroneDataBuddy
docker-compose up 
docker-compose stop
```

docker build --tag ardupilot .

docker run -it --rm -p 5761:5760 --env-file env.list ardupilot

Test:
mavproxy.py --master=tcp:localhost:5760


### Options
1. A PX4 and Ardupilot instance of SITL are both available.  Currently edit the docker-compose file to point to an alternative
    1.1] To change the behaviour, firmware version, startup conditions, or vehicle being simulated see the relevant README for instructions.  System defaults are set in the relevant (Ardupilot env.list)[ardupilot-sitl-docker/env.list] 


To change the vehicle type and version being simulated see SITL dockerfile README] 


## Design docs:
User Stories are outlined in:
* [Drone Developer](DDesignUserStories/DroneDeveloper_UserStories.md)
* [Pilot/Project PI](DesignUserStories/Pilot_UserStories.md)
* [Researchers](DesignUserStories/Researcher_UserStories.md)

![DroneDataBuddy Initial Design](DesignUserStories/images/Design1.png)
