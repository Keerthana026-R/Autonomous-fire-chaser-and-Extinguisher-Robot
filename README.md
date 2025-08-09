# Autonomous-fire-chaser-and-Extinguisher-Robot
A robot designed to detect fire using sensors, navigate towards the source, and automatically extinguish it using a water pump, enhancing safety in hazardous environments.

This project focuses on the development of an Autonomous Fire Chaser and Extinguisher Robot, aimed at enhancing fire safety and emergency response. The robot is designed to detect, approach, and extinguish fires autonomously.

It contains BO motors and motor driver to control the movement of robot. When it detects fire it communicates with microcontroller (Arduino MEGA) and the robot will move towards the fire a ected area. The robot remains idle initially, after detecting any burning object, it starts rotating in 360 degrees to detect the presence of burning object with the help of flame sensor. If the object is not within the range it moves ahead and then again checks the presence of object within the range. The signal is sensed to the one of the 3 channel flame sensor and then robot moves if it signals to center sensor so that it can move to the object accurately. After detecting the flame it moves to certain distance and again checks the range of distance until it moves near the flame object. After it reaches it then in turn activates fire extinguisher or water pump to sprinkle the water on fire object.

If the fire stops, then Robot stops sprinkling the water. Now, the Robot is moved to other location, where the fire is existing. The result of the research showed that this fire extinguisher robot can detect fire as far as it successfully extinguishes the fire. This robot will reduce the risk of injury for firefighters and possible victims and decrease the monetary losses which increase considerably as fire duration increases. The robot can be used in a place that has a small entrance or in small spaces because it has a compact structure.

ARCHITECTURE DIAGRAM 

                    [Flame Sensors (3 channels)]
                               |
                               v
                       [Arduino MEGA] 
                               |
                ------------------------------
               |                              |
     [Motor Driver]                 [Water Pump / Extinguisher]
               |                              |
               v                              |
    [BO Motors for Movement]                  |
               |                              |
               v                              v
     [Robot Movement towards Fire]    [Extinguishing the Fire]
               |
               v
       [Proximity Check and Repeat Process]
               |
               v
          [Return to Idle Mode]

  

WORKFLOW DIAGRAM


Start
  |
  v
[Idle Mode] -> (Flame Detected?)
  |                |
  No               Yes
  |                v
  |       [Rotate 360 Degrees to Detect Fire]
  |                |
  |        (Fire Location Identified?)
  |                |
  |     No         Yes
  |     |          v
  |     |     [Move Towards Fire]
  |     |          |
  |     |    (Close to Fire?)
  |     |          |
  |     |     No   Yes
  |     |     |    v
  |     |     | [Stop]
  |     |     |    |
  |     |     | [Activate Water Pump]
  |     |     |    |
  |     |     | (Fire Extinguished?)
  |     |     |    |
  |     |     No   Yes
  |     |     |    v
  |     |     | [Stop Water Pump]
  |     |     |    |
  |     |     v    v
  |     | [Move to Other Fire Location?]
  |     |    |         |
  |     |    Yes       No
  |     |    |         v
  |     v    v    [Return to Idle Mode]
  v
End
