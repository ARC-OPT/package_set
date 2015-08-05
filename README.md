# README #
This package set contains software libraries, components and GUIs related the   
topic of Whole Body Control, a reactive approach for controlling complex robotic  
systems based on *constraints*. This approach differs from traditional robot  
control in the sense that instead of directly specifying robot motions, e.g. by  
the means of a trajectory, only the properties of the robot behaviour are  
defined by constraining the allowed space of motion and a constraint solver   
takes care of the actual motion generation. This has the following advantages:
 * Complex behaviours can be specified by the means of combining simple  
   constraints
 * The capabilities of the whole body can be taken into account, which makes the  
   approach particularly interesting for the field of mobile manipulation
 * Robotic systems with a large number of DOF (>50) and multiple kinematic  
   subsystems (multiple arms, legs, etc.) can be controlled
 * Immediate reactions to unexpected changes in the environment are possible