Learning happens in a context: the system will look for descriminating features
The more the set of training data is restrited, the less it learns.
Negative weights exist in neuron networks.

Presynaptic / Postsynatpic
A synapse can be represented as weight.

Place cells:
allows to detect position
locoated in the hippocampus
hippocampus grows as taxi drivers learned the map of London.

Simplest neuron integration: sum of inputs

dentrites: trees of connection
axon: connects a neuron to a tree

- resting potential: neuron inactive (stable / equilibrium)
- threshold: value that has to be reached for the neuron to fire

- weights: change when learning, determin what the neuron detects
- integrate

Threshold avoids epilepsy.
A linear activation fuction:
- Would go up to infinity
- Sum of all input neurons (system is linear to input)

Having an asymptote make values saturate.

# Key concepts

- channels:
 - by which ions enteror leave neurons
 - type specific Na+, Cl-, K+ channels (Na+ exites, C- inhibits (flows in), K+ inhibits (flows out))
 - K+ channl is a leak (will pull potential back down)
 - also excitation and inhibtion specific (although not a one-to-one relation)
- Charge oppoites attract, likes repel
- Electric potential (difference in charge, aka voltage)
 - amount of oppsite charge that can be attracted to that area
 - difference in concetration of charged atoms
- membrane potential -> neuron's level of exitation
 - neuron potential most often negative (charge in membrane lower than charge of surrounding)
 - extra cellularspace effectivly zero
- voltage gated channles
 - open when membrane potential crosses particular threshold

Resting potential:
- no input
- steady state in absence of stimulation
- -70mV due to Na/K pump (electrically primed)
Action potential
- electrical pulse released when threshold is crossed, releases neurotransmitter
- neurotransmitter activates potential via synaptic input channels
Resistance
- level of obstruction to ion flow e.g. opening of channels


Equilibrium channel potentials != Equilibrium membrane potentials

- Balance of electric of diffusion forces
- Ion channel equilibrium
- principal ios
- Intergation qutions
- The overall membrane quilibrium potential

# Resistance:

OHM's law

I = V / R
Conductance G = 1 / R
I = V * G

# Diffusion
Constant motion causes mixing. (equilibration of molecule count)

E = euilibrium = amount of electrical potential needed to counterat diffusion:

I = G * (V - E)

Also called:
Reversal potenetial (because current reverses on either side of E)
Driving potential (flow of ions drives potential towards this value)

Each ion channel has its own equilibrium potential

Equilibrium of leak channel is the neuron resting potential

Lowest potential = leak channel equilibrium potential.

K+ leaks, and causes the leak channel equilibrium potential
Na+ and Cl- flows are what cause the equilibrium potential for other channels

Current for an arbitrary channel c:

Ic(t) = Gc(t) * /Gc * (Vm(t) - Ec)

Gc(t): Fraction c channel open at time t
/Gc: Maximum conuctance if channel fuly open
Vm(t): Membrane potential at time t
Ec: Eqilibrium potential for channel

Gl(t) = 1

I_net(t) = Ge(t) * /Ge * (Vm(t) - Ee) + // Excitatory: Na+
     	   Gi(t) * /Gi * (Vm(t) - Ei) + // Inhibitory: Cl-
     	           /Gl * (Vm(t) - El)   // Leak: K+

At equilibrium membrane potential I_net(t) = 0

Vm (t + 1) = Vm(t) + dt_Vm * I_net(t)
      	   = Vm(t) + dt_Vm * [
	   	   Ge(t) * /Ge * (Ee - Vm(t)) + // Excitatory: Na+
	 	   Gi(t) * /Gi * (Ei - Vm(t)) + // Inhibitory: Cl-
     	                   /Gl * (El - Vm(t))   // Leak: K+
		   ]

dt_Vm is just a time constant.
Note that I_net has been inverted, so that exictation goes upwards.
At equilibrium mebrane potential, Vm doesn't change.

At equilibrium:

Vm(t) = (Ge(t) * /Ge * Ee
       + Gi(t) * /Gi * Ei
       	       + /Gl * El)
      / (Ge(t) * /Ge
       + Gi(t) * /Gi
       	       + /Gl)

