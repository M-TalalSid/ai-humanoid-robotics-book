---
title: Actuators, Motors & Locomotion
sidebar_position: 6
description: Actuators, motors, and locomotion systems in humanoid robots
---

# Actuators, Motors & Locomotion

## Introduction to Actuation Systems

Actuation systems form the musculature of humanoid robots, converting electrical energy into mechanical motion. These systems must provide precise control, sufficient force, and appropriate compliance to enable human-like movement and interaction.

### Actuator Requirements

Humanoid robot actuators must meet several critical requirements:

- **Precision**: Accurate positioning and force control
- **Power density**: High force/torque output relative to size and weight
- **Compliance**: Ability to safely interact with humans and environments
- **Efficiency**: Minimizing power consumption for battery operation
- **Reliability**: Long-term operation without failure
- **Backdrivability**: Ability to be moved by external forces when needed

## Motor Technologies

### Brushless DC Motors

Brushless DC (BLDC) motors are widely used in humanoid robots:

#### Advantages
- **High efficiency**: Better than brushed DC motors
- **Long life**: No brushes to wear out
- **High power density**: Good torque-to-weight ratio
- **Precise control**: Electronic commutation allows for accurate positioning

#### Construction
- **Stator**: Fixed electromagnets arranged in phases
- **Rotor**: Permanent magnets that rotate
- **Electronic controller**: Replaces mechanical commutator
- **Position feedback**: Required for proper commutation

#### Applications
- **Joint actuators**: Primary choice for most humanoid joints
- **High-performance requirements**: Where efficiency and precision are critical
- **Long-term operation**: Applications requiring extended lifetime

### Servo Motors

Servo motors integrate motor, controller, and feedback in a single package:

#### Components
- **Motor**: Usually a DC or BLDC motor
- **Gearbox**: Provides torque multiplication and speed reduction
- **Controller**: Closed-loop position/velocity control
- **Feedback**: Encoder or potentiometer for position sensing

#### Control Types
- **Position control**: Move to specific angular position
- **Velocity control**: Control angular velocity
- **Torque control**: Control output force/torque
- **Compliance control**: Control stiffness and damping

#### Performance Characteristics
- **Resolution**: Depends on encoder resolution
- **Speed**: Limited by gear ratio and motor characteristics
- **Torque**: Multiplication provided by gearbox
- **Backlash**: Gear system introduces some backlash

### Specialized Motor Types

#### Series Elastic Actuators (SEA)

SEAs incorporate a spring in series with the motor:

##### Advantages
- **Inherent compliance**: Safe human interaction
- **Force sensing**: Spring deflection indicates output force
- **Shock absorption**: Protects motor from impact loads
- **Energy storage**: Spring can store and release energy

##### Design Considerations
- **Spring selection**: Stiffness affects performance characteristics
- **Control complexity**: Requires advanced control algorithms
- **Size constraints**: Additional components increase size
- **Tuning**: Spring and control parameters must be carefully matched

#### Variable Stiffness Actuators (VSA)

VSAs can actively change their compliance:

##### Mechanisms
- **Adjustable springs**: Physical adjustment of spring stiffness
- **Antagonistic actuation**: Two actuators opposing each other
- **Variable transmission**: Changing mechanical advantage

##### Applications
- **Safe interaction**: Adapting compliance to task requirements
- **Energy efficiency**: Optimizing for different movement types
- **Versatile manipulation**: Different stiffness for different tasks

## Transmission Systems

### Gear Reduction

Most actuators require gear reduction to achieve appropriate torque and speed:

#### Harmonic Drives
- **Advantages**: High reduction ratios in compact size, low backlash
- **Construction**: Wave generator, flex spline, and circular spline
- **Efficiency**: High efficiency with proper lubrication
- **Applications**: Precision joints requiring high torque

#### Planetary Gears
- **Advantages**: High torque capacity, coaxial input/output
- **Construction**: Sun gear, planet gears, and ring gear
- **Efficiency**: Good efficiency with proper design
- **Applications**: High-load joints like hips and knees

#### Cycloidal Drives
- **Advantages**: High reduction ratios, zero backlash
- **Construction**: Eccentric bearing and cycloidal disc
- **Efficiency**: Good efficiency with proper design
- **Applications**: Critical joints requiring precision

### Direct Drive Systems

Some applications use motors without gear reduction:

#### Advantages
- **No backlash**: Direct connection eliminates gear backlash
- **High bandwidth**: Faster response to control commands
- **Backdrivable**: Easy to move when unpowered
- **Low maintenance**: Fewer wearing components

#### Disadvantages
- **Size constraints**: Large motors needed for high torque
- **Speed limitations**: High-speed motors may require gearing
- **Cost**: High-torque direct drive motors are expensive

#### Applications
- **Low-torque joints**: Where high torque is not required
- **High-precision applications**: Where backlash is problematic
- **Backdrivability requirements**: Where manual positioning is needed

## Locomotion Systems

### Bipedal Walking Fundamentals

Bipedal locomotion in humanoid robots requires sophisticated control:

#### Balance Control
- **Zero Moment Point (ZMP)**: Maintaining ground reaction forces within support polygon
- **Capture Point**: Location where robot must step to stop safely
- **Pendulum models**: Linear Inverted Pendulum Model (LIPM) for simplified control
- **Feedback control**: Real-time adjustment based on sensor feedback

#### Walking Patterns
- **Static walking**: Maintaining stability at all times (slow but stable)
- **Dynamic walking**: Controlled falling and recovery (more human-like)
- **Pre-planned trajectories**: Open-loop patterns with feedback correction
- **Adaptive patterns**: Real-time adjustment to disturbances

### Step Planning and Execution

#### Footstep Planning
- **Terrain analysis**: Identifying suitable step locations
- **Stability constraints**: Ensuring each step maintains balance
- **Obstacle avoidance**: Planning around obstacles
- **Dynamic constraints**: Accounting for robot dynamics

#### Swing Leg Control
- **Trajectory generation**: Smooth motion from stance to swing position
- **Ground clearance**: Avoiding obstacles during swing phase
- **Impact minimization**: Reducing forces when foot contacts ground
- **Timing coordination**: Synchronized with support leg control

### Advanced Locomotion Techniques

#### Dynamic Walking
- **Passive dynamic walking**: Using gravity and momentum
- **Limit cycle control**: Stable periodic walking patterns
- **Energy efficiency**: Minimizing power consumption during walking
- **Speed variation**: Adjusting walking speed as needed

#### Terrain Adaptation
- **Uneven terrain**: Adapting to varying ground heights
- **Slippery surfaces**: Adjusting for reduced traction
- **Obstacle negotiation**: Stepping over or around obstacles
- **Recovery strategies**: Responding to unexpected disturbances

## Control Strategies

### Low-Level Motor Control

#### PID Control
- **Proportional term**: Corrects for position error
- **Integral term**: Eliminates steady-state error
- **Derivative term**: Dampens oscillations
- **Tuning**: Critical for stable and responsive performance

#### Advanced Control Methods
- **Model-based control**: Using robot dynamics in control
- **Adaptive control**: Adjusting parameters based on changing conditions
- **Robust control**: Maintaining performance despite uncertainties
- **Optimal control**: Minimizing specific cost functions

### High-Level Locomotion Control

#### Central Pattern Generators (CPGs)
- **Biological inspiration**: Mimicking neural circuits that generate rhythmic patterns
- **Adaptive behavior**: Responding to sensory feedback
- **Rhythmic patterns**: Generating coordinated joint movements
- **Simplicity**: Reducing computational requirements

#### Model Predictive Control (MPC)
- **Predictive capability**: Anticipating future states
- **Optimization**: Minimizing cost over prediction horizon
- **Constraints**: Handling physical and safety constraints
- **Real-time implementation**: Solving optimization problem in real-time

## Power and Efficiency Considerations

### Energy Management

#### Power Consumption
- **Motor efficiency**: Optimizing for specific operating conditions
- **Control efficiency**: Minimizing energy in control electronics
- **Transmission efficiency**: Reducing losses in gear systems
- **Standby power**: Minimizing consumption during inactivity

#### Battery Life Optimization
- **Efficient walking**: Minimizing energy per unit distance
- **Adaptive control**: Reducing power when full capability not needed
- **Power management**: Shutting down unused systems
- **Regenerative systems**: Recovering energy where possible

### Thermal Management

#### Heat Generation
- **Motor heating**: Managing heat from electrical losses
- **Gear heating**: Friction losses in transmission systems
- **Control electronics**: Heat from power electronics
- **Dissipation**: Designing for adequate heat removal

#### Cooling Systems
- **Passive cooling**: Natural convection and radiation
- **Active cooling**: Fans or liquid cooling systems
- **Thermal design**: Heat sinks and thermal pathways
- **Temperature monitoring**: Preventing overheating

## Safety and Compliance

### Human Safety

#### Collision Safety
- **Compliance design**: Using compliant actuators to reduce impact forces
- **Force limiting**: Controlling maximum output forces
- **Emergency stops**: Rapid shutdown of actuator power
- **Safe states**: Default positions when power is removed

#### Operational Safety
- **Limit switches**: Preventing motion beyond safe ranges
- **Current limiting**: Protecting motors from excessive loads
- **Temperature protection**: Preventing overheating
- **Communication monitoring**: Detecting control system failures

### Environmental Protection

#### Enclosure Design
- **IP ratings**: Protection against dust and moisture
- **Sealing**: Preventing contamination of internal components
- **Ventilation**: Managing heat while maintaining protection
- **Maintenance access**: Allowing service while maintaining protection

## Integration Challenges

### Mechanical Integration

#### Packaging
- **Space constraints**: Fitting actuators within limb structures
- **Weight distribution**: Maintaining center of gravity
- **Cable routing**: Managing power and communication cables
- **Thermal management**: Providing adequate cooling

#### Mounting and Support
- **Structural loads**: Supporting actuator weight and reaction forces
- **Vibration isolation**: Preventing vibration transmission
- **Alignment**: Maintaining proper mechanical alignment
- **Accessibility**: Allowing for maintenance and replacement

### Control Integration

#### Coordination
- **Multi-joint control**: Coordinating multiple actuators for movement
- **Timing synchronization**: Ensuring coordinated motion
- **Load sharing**: Distributing loads across multiple actuators
- **Fault tolerance**: Maintaining function with partial failures

#### Communication
- **Real-time requirements**: Meeting timing constraints for control
- **Bandwidth management**: Handling multiple communication channels
- **Protocol selection**: Choosing appropriate communication protocols
- **Network reliability**: Ensuring communication integrity

## Future Developments

### Advanced Actuator Technologies

#### Artificial Muscles
- **Electroactive polymers**: Materials that contract when electrically stimulated
- **Pneumatic muscles**: Air-powered actuators with muscle-like properties
- **Advantages**: High compliance, lightweight, backdrivable
- **Challenges**: Control complexity, durability, efficiency

#### Bio-inspired Actuators
- **Tendon-driven systems**: Mimicking biological muscle-tendon arrangements
- **Parallel mechanisms**: Multiple actuators working together
- **Advantages**: Natural compliance, energy storage
- **Applications**: More human-like movement and interaction

### Control Innovations

#### Learning-based Control
- **Reinforcement learning**: Learning optimal control strategies
- **Imitation learning**: Learning from human demonstrations
- **Adaptive control**: Adjusting to individual robot characteristics
- **Applications**: Improving performance over time

#### Hybrid Control Approaches
- **Model-free and model-based**: Combining different control methods
- **Hierarchical control**: Multiple control layers with different objectives
- **Optimization-based**: Using optimization for complex control problems
- **Real-time adaptation**: Adjusting control parameters online

---

*This chapter covers actuators, motors, and locomotion systems in humanoid robots, focusing on the key systems that enable movement and mobility.*