### PEAS Description (Performance measure, Environment, Actuators, Sensors)

|**Component**|**Description for Automobile Driver Agent**|
|---|---|
|**Performance Measure**|- Safe driving (no accidents) - Reaching destination in minimal time - Fuel efficiency - Obeying traffic rules|
|**Environment**|- Roads and traffic - Other vehicles - Pedestrians - Traffic signals - Weather conditions|
|**Actuators**|- Steering wheel - Accelerator - Brake - Gear control - Horn|
|**Sensors**|- GPS - Speedometer - Cameras (for lane/traffic detection) - Radar/LiDAR - Proximity sensors - Microphones|
### State Space Description

- The **state** represents a snapshot of all relevant information at a particular moment.

- For the Automobile Driver Agent, a **state** may include:
   
```js
State = {
  current_position (latitude, longitude),
  current_speed,
  direction,
  nearby_vehicles and their speeds,
  traffic signal status,
  lane position,
  road condition,
  destination location,
  weather condition
}
```

- The **state space** is the set of all such possible states the car might be in, given all combinations of position, speed, traffic, environment, etc.