# Drone developer/deployer user stories
- Assumption1: There is a companion computer mounted on the drone and that this may handle only information about the drone or it may additionally also handle information about the sensor payloads.
- Assumption2: Sensor payloads are modular and may have their own companion computer
- Assumption3: The following tasks are done with connectivity to the internet available
- Assumption4: The companion computer is hosting a webserver as a means of prviding an interface to its data and services and the following tasks are completed by interacting with webforms served by this computer.  Access to these webforms may be via latop/phone/alternative.

### Task: Configure Server
* Assume a web-connected server of sufficient resources running a DroneDataBuddy-Configuration service

1. Select Data DB type
2. Select Schema 
3. Define Data DB endpoint(s)
4. Define a tripple store type
5. Select Schema 
6. Define tripple store endpoint(s)
//Wishlist: Configure self publications DB, Schema, endpoints

### Task: Configure Companion Computer
1. Access DroneDataBuddy service via webpage as hosted onboard comapnion computer
2. Add server end point for local publication of gathered data

### Task: Drone instantiation with compute and no autopilot integration scenario
 - Assumes the companion computer has not been connected to the autopilot, such as is likely the case with a DJI platform
 - Results in the creation of a URI associated with each drone

1. Go to add autopilot configuration form (metadata entry only, no configuration capabilities) being served by companion computer and capture:
    * Drone legal registration number
    * Drone model
    * Drone manufacturer
    * Drone frame type (quad/boat/wing/rover/etc)
    * Optional: drone configuration provenance information (eg lab tech/software)
2. Store information locally
3. Publish information to offboard server
4. Optionally review and edit information

### Task: Drone instantiation with compute and autopilot integration scenario
- Assumes autopilot is running either Ardupilot or PX4 and has hardware support for additional serial connectivity and using Mavlink 2
- Assumes drone and autopilot is fully configured using drone specific software:  load latest firmware, set UxS model, calibrate flight sensors, GPS, handheld radio, battery 
- Assumes the companion computer has been connected to the autopilot
- Results in the creation of a URI associated with each drone

1. Go to add autopilot configuration form (metadata entry only, no configuration capabilities) being served by companion computer.  Service attempts to connect to autopilot and prepopulates form as far as possible or notifies user of connection failure.  The following therefore may have been autopopulated but can also be manually added:
    * Drone legal registration number
    * Drone model
    * Drone manufacturer
    * Drone frame type (quad/boat/wing/rover/etc)**
    * Optional: drone configuration provenance information (eg lab tech/software)**
    * Autopilot hardware Model**
    * Interface**
    * Interface port**
    * Firmware type and version**
2. Store information locally
3. Publish information to offboard server
4. Optionally review and edit information      
\*\*Potentially prepopulated

### Task: Sensor instantiation scenario 
- Assumes a sensor *can* be connected to companion computer in a manner that allows data from the server to be stored by the companion computer
- Results in the creation of a URI associated with each sensor

1. Go to add sensor configuration form (metadata entry) being served by companion computer.  If this is going to be similar to an existing sensor select 'copy sensor' to get a prepopulated version to be modified
    * Sensor Make and Model
    * Sensor sampling rate
    * Sensor measurement capability (observable properties with units)
    * Sensor firmware
    * Sensor Interface
    * Sensor port
    * Sensor mount method
    * Sensor mount location
    * If an altitude sensor, add information regarding what altitude it is sensing
2. Optionally add calibration information
3. Store information locally
4. Publish sensor information to offboard
5. Optionally review and edit all sensor already configured
6. Repeat process to attach additional sensors
//Wishlist: At a future date this form could be used to also configure some of the above parameters if the backend integration is done

### Task: Drone platform instantiation scenario 
- Assumes drone(s) has already been instantiated 
- Assumes sensor(s) has already been instantiated 
- Results in the creation of a URI associated with each drone platform

1. Go to add drone platform configuration form (metadata entry) being served by companion computer 
2. Select drone
3. Select sensor(s)
4. Store information locally
5. Publish sensor information to offboard




