# Computational Neurons

1. discrete spiking
2. rate coded -> don't emulate emultiple individual spikes, but model rate of spikes

How do spiking learning models work?

## ANN vs Point Neurons

- Point neuron has seperate input channels
- In ANNs a signke neuron can have both inhibiritory and excitory ouptut links
  Not justified by biology neaurons are either inhibitory or exitatory
  Could be exmplained by an inhibitory in the middle of an inhibitory connection
- ANNs: weights can change sign through learning
  Biology implausible
- In point neurons, net inputs are converted into a membrane potential, then a further function turns this into an ouptu
  In ANNs, all done in one step

## ANN

net input = sum of all channel inputs multiplied by their weight

y: activation value

y = 1 / (1 + e ^ -net input)

A threshold c can be introduced

y = 1 / (1 + e ^ -(net input - c))

## Point neuron

"<>" means average

Ge = <x_i * wij> + Beta / N
Vm = (Ge * /Ge * Ee
    + Gi * /Gi * Ei
         + /Gl * El)
   / (Ge * /Ge
    + Gi * /Gi
       	 + /Gl)
Yj = gamma * |Vm - theta| /
    (gamma * |Vm - theta|  + 1)
Yj: spikes or rate coe

Gi is for later.

| Parameter | mV  | normalised |
|-----------|-----|------------|
| Vrest	    | -70 | 0.15       |
| El	      | -70 | 0.15       |
| Ei	      | -70 | 0.15       |
| theta	    | -55 | 0.25       |
| Ee	      | +55 | 1.00       |

## Output functions

