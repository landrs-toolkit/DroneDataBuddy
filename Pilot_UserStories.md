# Pilot/PI user stories:
* Note: for drone data collecting projects the heriarchy used in the following is:
  - Project > Campaign(s) > Flight(s)

## Server use

### Task: Configure Server
* Assume a web-connected server of sufficient resources

1. Select Data DB type
2. Select Schema 
3. Define Data DB endpoint(s)
4. Define a tripple store type
5. Select Schema 
6. Define tripple store endpoint(s)
//Wishlist: Configure self publications DB, Schema, endpoints

## Drone use
* Assume a companion computer onboard the drone that is (i) connected to the autopilot, and (ii) hosting a webserver as a means of prviding an interface to its data and services
* Some of the following may be done in a web connected environment but others will be done while in the field where there is no internet connection
* All information should be stored onboard the drone.  Most of it is additionally also synced with a 'local store' (most likely a research lab server), and some of it will further be published to the world in other 'Researcher user stories'
* When in the field the a wireless connection to the drone is possible (eg by the drone providing an access point itself or connecting to another)

### Task: Plan a flight
* Note, this might be retroactively - i,e after a flight has been completed
1. Select drone platform (drone plus sensors) from dropdown of available drone platform uris
2. Select Pilot and observers (as URIs) and/or from dropdowns
3. Select a flight plan from available (these are created using an external application and are files to be imported)
4. Define local data archive URI
5. Publish information captured thus far to local archive


### Task: Plan a project 
* Done in the lab with web connectivity
* Using the drone provided webinterface:

1. Capture project information:
    * Project(s), Funder(s) award, Funder(s) organisation, PI, PI organisation //reuse EU from RDA science graph/wiki
    * Duration
    * Project policy (data use, operations, drone/data/pilot/operations licenses)
    * Project components (drone data capture, manual data capture, interviews, data analyses, travel, publications)
2. Define data structures within the design of your project and capture data about these
   * Project (A hypothesis goal)
      - Event Campaign1 (Mission): Could be a time period eg a week, or a site eg field A/B
         - Event Flight1 (Collect)
         - Event Flight2
     - Event Campaign2
         - Event Flight3
         ...
3. Define local data archive URI
4. Publish information captured thus far to local archive


### Task: Plan a campaign(s)
Note: 3 types of campaigns exist:
 - Coverage of a feature of interest
 - Repeated sampling 
 - Dynamic response

1. Capture campaign planning information
    * Spatial footprint of campaign
        * Geo Feature: An agricultural field //Machine fetch from GNIS LD  and/or Openstreetmap
            * Feature of interest: Farmer Fred’s field called West field //Also possibly publicly available information
                * Has Feature(s) of interest: Underground drainage pipe
                * Has observable property IR spectra difference
    * Temporal Duration of campaign
    * How many flights total
    * Schedule of flights
    * Launch/Landing sites
    * Data capture plan as URI (see next task)
    * Capture Pilot and observers (as URIs)
    * Schedule of drone maintenance
    * Plan legal stuff (access etc)
    * Select drone platforms (aircraft plus sensors) to be used from list of available 
    // Wishlist: Data post-processing plan 
2. Repeat for each additional project campaign
3. Define local data archive URI
4. Publish information captured thus far to local archive

### Task: Create a data capture plan
* Done in the lab with web connectivity
* Likely done per campaign or per project but could be done for each flight
* Using the drone provided webinterface:

Note: 2 scenarios
    - Autopilot configures sampling (eg triggers camera)
    - Other service configures sampling (eg local script/sensor driver/sensor configuration itself)

1. Add data source and capture information:
    * Select sensor URI (or add new sensor if not yet registered)
    * Sensor output format and schema (select LD terms)
    * Sampling frequency/other info
    * What autopilot metadata do you want to capture alongside this sensor's data in the same file
    * Timestamp source
    * Output file format
    * Have optional page to collect additional information related imagery specifically
2. Repeat (1) for each sensor
3. Define a preflight metadata checklist and assign a URI
   * Mission (flight plan as created in external planning software)
   * Calibration image or ground data sampling
   * Legal checklists
4. Define a postflight metadata and assign a URI
   * Post-flight Calibration image or ground data sampling
   * Flight log 
   * Legal checklists
5. Select/Define local data archive URI for this DMP information endpoint
6. Select/Define local data archive URI for the intended flight data 
6. Publish information to local archive
// Wishlist: Optional page to configure realtime monitoring configuration (MQTT/Mavlink/COAP/NBIoT/ROS)

### Task: Capture Flight Data
* Done in the field likely without web connectivity
* Using the drone provided webinterface:

1. Capture preflight metadata by going through previosuly created preflight checklists
2. Trigger sensor start capture with feedback showing correct operation (optionally opens realtime monitoring interface)
3. Fly flight.  
4. Trigger sensor stop capture and on 'stop', tag captured data with: Project ID, DMP ID, Flight ID, Pre and post flight metadata IDs
5. Capture postflight metadata by going through previosuly created preflight checklists
6. Repeat for as many flights as required with warnings if space is running out
7. Once web connectivity is restored (back in lab/other) automatically publish all collected data to local archive as configured
8. Publish above to remote archive eg wikidata/some drone data portal
//Wishlist: During flight upload to cloud
