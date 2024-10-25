# Animations, Pendula, Runge Kutta Formula
* Modify the particle in a bouncing box to have be on a TV screen with a 3:4 ratio as seen in [The Office](https://www.youtube.com/watch?v=QOtuX0jL85Y)
* Observe how the single pendulum gains energy and changes modes between simple harmonic motion and wrap-around behaviours.

* Model a cannon-ball under the effects of air resistance.
    * The ball is subject to gravity F = mg, vertically 
    * A good air resistane model has a force proportional to the absolute square of velocity opposing the motion, F = -γ |v|^2 v_hat. (v_hat is the unit vector in the velocity direction)
* Have the cannon ball elastically bounce off the floor.

* Add air resistance to the pendulum.
    * Using the model above
    * Using a linear in velocity model, F = -γ v

* Observe the effect of the unstable point in the pendulum by setting the initial condition to `{π, 0}` which is the inverted state.
    * Mathematically, it should stay here forever, does it?
    * what controls for how long it is upright?
