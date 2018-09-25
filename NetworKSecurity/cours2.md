# The Physical Layer

## Data Communication Theory

### Data rate

bits transmitted / time
bps -> *bits* per second
I.e: 50 bytes per second -> 400 bits per second

Latency: it's posssible to move data very cheaply physicly, but the latency is huge.

(Transfering tpes can reach 13 Tbps)

## Electronic signals

300 000 km/s in air/space, 200 000 km/s in air

### Analog signals

- amplitude of analog can vary continuonlsy
- used for radio / phone for 1°° years

### Digital signals

- finite amount of fixed levels

### Atenuation

- singals lose power
- signals get distorted
- distortion depends on data rate and *bandwidth*

Effects can be reduced with higher quality cable.

### Distortion vs Data Rate

Distortion can have limited effect.
Loss of high frequency content.

Increasing rate increasses bps but also increases distortion

### Nyquist Limit (for distortion)

```
H -> difference between high and log freq
V -> number  of levels
 
2 * H * log2(V) bps
```

!!! Find out if nyquistic frequency is a hard limit. !!!

### Noise

- Thermal noise (aka. white noise), present on all physical systems
- Cross talk: signals from other channels
- Impulse noise (intermittent): power surges, lightning strikes

Signal to noise ratio.
Using more levels causes SNR to increase.

### Shanon Limit (for Noise)

```
SNR -> signal pover / noise power
H -> difference between high and log freq

H * log2(1 + SNR)
```

Accurate for Thermal noise and Cross talk.
