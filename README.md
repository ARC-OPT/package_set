## Whole Body Control ##

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
 
A constraint will always be associated to a controller, which provides the  
input for the constraints. In practice this will typically be some kind of  
gradient, which regulates a particular subtask, e.g. the output of a position 
controller. 
 
Constraints can be specified in Cartesian and in joint space. Each constraint  
has a priority, which defines its relative importance with respect to the other  
constraints. A constraint with lower priority will not influence any constraint  
with higher priority (by using nullspace projections). However, it is also  
possible to give all constraints equal priority. In that case the solver will    
try to satisfy all constraints 'as good as possible'. Task weights can be used   
to weight the relative importance of constraints with equal priority. 

The following software components are provided:

* `wbc`: The main wbc library. Contains in particular the constraint solver, which is   
largely based on the iTaSC implementation, a KDL-based robot model and other  
tools. 
* `orogen-wbc`: The component interface for the wbc library. 
* `ctrl_lib`: The control library. Here you can find a couple of controller, like PID,  
potential fields or feed-forward position controllers. 
* `orogen-ctrl_lib`: The component interface for the control library.
* `wbc_status_gui`: A graphical interface for the wbc component. Shows the output  
of the solver and the status of all configured constraints. Also provides the  
possibility to activate/deactivate constraints.
* `wbc_ctrl_gui`: A graphical interface for the ctrl_lib components. Can be used  
to provide setpoints for the controllers and change control parameters.