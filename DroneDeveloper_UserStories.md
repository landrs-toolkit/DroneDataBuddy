# User stories

## Drone developer stories
- Assumption1: There is a companion computer which may handle only information about the drone or it may additionally also handle information about the sensor payloads.
- Assumption2: Sensor payloads are modular and may have their own companion computer

### Drone instantiation with companion computer and no autopilot integration
- Assumes in lab with web access

1. Attach companion computer to drone (this creates a platform)
2. Connect web browser capable device to companion computer
3. Access drone payload dashboard
4. Optionally add URIs for offboard publication 
5. Go to add autopilot configuration form (metadata entry only, no configuration capabilities) being served by companion computer.
    * Drone legal registration number
    * Drone model
    * Drone manufacturer
    * Drone frame type (quad/boat/wing/rover/etc)
    * Optional: drone configuration provenance information (eg lab tech/software)
6. Store information locally
7. Publish information to offboard
8. Optionally review and edit information


### Drone instantiation with companion computer and autopilot integration
 - Assumes in lab with web access
 - Assumes autopilot is running either Ardupilot or PX4 and has hardware support for additional serial connectivity and using Mavlink 2
 - Assumes drone and autopilot is fully configured using drone specific software:  load latest firmware, set UxS model, calibrate flight sensors, GPS, handheld radio, battery 

1. Attach companion computer to drone autopilot (this creates a platform) via serial telemetry interface using Dronekit Python (or other drone specific interface and SDK) 
2. Connect web browser capable device to companion computer
3. Access drone payload dashboard
4. Optionally add URIs for offboard sensor publication 
5. Go to add autopilot configuration form (metadata entry only, no configuration capabilities) being served by companion computer.  Service attempts to connect to autopilot and prepopulates form as far as possible or notifies user of connection failure:
    * Drone legal registration number
    * Drone model
    * Drone manufacturer
    * Drone frame type (quad/boat/wing/rover/etc)**
    * Optional: drone configuration provenance information (eg lab tech/software)
    * Autopilot hardware Model**
    * Interface
    * Interface port**
    * Firmware type and version**
**Potentially prepopulated
6. Store information locally
7. Publish information to offboard
8. Optionally review and edit information

### Sensor attachment scenario 
 - Assumes drone is instantiated with a payload companion computer
 - Assumes in lab with web access

1. Attach usb over serial interface capable K33 sensor whos python module driver has the observed properties: Relative humidity, Ambient Temperature, CO2 ppm,  to a companion computer
2. Connect web browser capable device to companion computer
3. Access drone payload dashboard
4. Go to add sensor configuration form (metadata entry/literal configuration) being served by companion computer (Another scenario this could be done via latop/phone/alternative):
    * Sensor Make and Model
    * Sensor sampling rate
    * Sensor measurement capability (observable properties with units)
    * Sensor firmware
    * Sensor Interface
    * Sensor port (can be autopopulated)
    * Sensor mount method
    * Sensor mount location
    * If an altitude sensor, add information regarding what altitude it is sensing
5. Optionally add calibration information
6. Store information locally
7. Publish sensor information to offboard
8. Optionally review and edit all sensor already configured
9. Repeat process to attach additional sensors

### Trajectory source selection and configuration scenario
 - Assumes drone is instantiated with a payload companion computer
 - Assumes autopilot is running either Ardupilot or PX4 and has hardware support for additional serial connectivity and using Mavlink 2
 - Assumes in lab with web access

1. Connect web browser capable device to companion computer
2. Access drone payload dashboard
3. Access trajectory selection form and select:
    * GPS source
    * Altitude source
    * Orientation source
    * Time source 
4. Optionally publish configuration to offboard
5. Optionally review and edit configured


