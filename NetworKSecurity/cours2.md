# The Physical Layer

## Data Communication Theory

### Data rate

bits transmitted / time

**b**ps -> ***bits** per second*

I.e: 50 *bytes* per second -> 400 *bits* per second

Latency: it's posssible to move data very cheaply physicly, but the latency is huge.

(Ex: Transfering tapes between London and Kent can reach 13 Tbps, but has a 1 hour latency)

## Electronic signals

300 000 km/s in air/space, 200 000 km/s in air

### Analog signals

- amplitude of analog can vary continuonlsy
- used for radio / phone for 1°° years

### Digital signals

- finite amount of fixed levels

## Attenuation

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

Tips to help remember: given a series of samples, you can recreate a function using a sum of `sin` functions:

```
f -> base frequency
A -> a series of values
Ak -> 'k'th value of this serie.

for all k : Ak * sin(k * f * t)
```

If we assume that `H` the rate of the samples is a musltiple of `f`, you'll notice the `sin(2 * s)` is completly invisible, so we can't recreate it. Higher frequencies will either be distorted or converted to a lower rate (sampling them will give a lower frequency `sin`). This means that our highest precision is `2 * H`.

Note: in the real formula, `H` is the frequency *bandwidth*, not the sampling rate. Our example is a simplification where the  lower bound of 0Hz, thus giving us a  bandwidth of `sample rate - 0`.

The `log2(V)` term comes from te fact that encoding `V` levels gives us `log2(V)` bits. (Ex: 4 levels gives us 2 bits).

Okish wikipedia aritcle on the subject: [link](https://en.wikipedia.org/wiki/Nyquist_rate)

## Noise

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
