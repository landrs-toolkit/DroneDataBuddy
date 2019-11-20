# User stories

## Pilot/PI user scenarios
* Some of the following can be done in a web connected environment but others are done while in the field where there is no internet connection
* When in the field the Drone provides a wifi access point when near a known wifi access point it will connect to that
* The drone provides a webserver 
### Plan a project 

1. Capture project information:
    * Project(s), Funder(s) award, Funder(s) organisation, PI, PI organisation //reuse EU from RDA science graph/wiki
    * Duration
    * Project policy (data use, operations, drone/data/pilot/operations licenses)
    * Project components (drone data capture, manual data capture, interviews, data analyses, travel, publications)
2. Define data structure within the design of your project and capture data about this
    * Project (A hypothesis goal)
        - Event Campaign1 (Mission): Could be a time period eg a week, or a site eg field A/B
        - Event Flight1 (Collect)
        - Event Flight2
        - Event Campaign2
3. Define local data archive URI
4. Publish to local archive
5. Publish above to wikidata

### Data capture plan
Note: 2 scenarios
    - Autopilot configures sampling
    - Other service configures sampling

1. Add data source and capture information:
    * Sensor output format and schema (select LD terms)
    * Sampling frequency/other info
    * What autopilot metadata do you want to capture too
    * Timestamp source
    * Output file format
    * What ground metadata are your capturing
    * Preflight
    * Postflight
    * If imagery click here to add image specific metadata
    * Realtime monitoring configuration (MQTT/Mavlink/COAP/NBIoT/ROS)
    * Wishlist: Configure Annotated realtime streams for consumption
2. Repeat above for each sensor

### During flight upload //Is a future wishlist

### Post flight data download off drone
**Onboard**
1. Configure:
    * Enter DB URI
    * wifi access point
    * upload condition
    * what to be downloaded
    * Any preprocessing
2. Tag data with FlightID
3. Attach flight log
4. Attach Pilot annotations


i**Server side**
1. Select DB
2. Select Schema
3. Define URI

### Plan a campaign
Note: 3 types of campaigns exist:
 - Coverage of a feature of interest
 - Repeated sampling 
 - Dynamic response

1. Capture planning information
    * Spatial footprint of campaign
        * Geo Feature: An agricultural field //Machine fetch from GNIS LD  and/or Openstreetmap
            * Feature of interest: Farmer Fred’s field called West field //Also possibly publicly available information
                * Has Feature(s) of interest: Underground drainage pipe
                * Has observable property IR spectra difference
    * Temporal Duration of campaign
    * How many flights total
    * Schedule of flights
    * Launch/Landing sites
    * Data management plan
        * Data archive structure
        * Data processing plan 
        * Ground metadata required
    * Pilot and observers (as URIs)
    * Schedule drone maintenance
    * Plan legal stuff (access etc)
    * Drones and sensors/sensor platforms to be used
2. Create Dataset metadata

### Plan a flight

1. Select mission plan as output from flight planning software (QGC/MissionPlanner/AMP Planner)
2. Select drone from dropdown
3. Select Pilot and observers (as URIs) and/or from dropdowns

Future: extend to include legal

