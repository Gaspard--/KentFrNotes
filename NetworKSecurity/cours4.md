# Digital communication via telephone networks

Reuse of existing inferstructure

# PSTN (Public Switched telephone Network)

- high noise (not ideal)

3 components:

- local loop: joins customer to network (CAT 3 utp)

- Switching office (telephone exchanges)
  Signal is converted to numeric

- Trunk lines (high bandwidth, fiber optic)

To adapt the data to the medium, a modem was uses.
Data is made to look like speech.

# Modems

(modulator-demodulatror)

- Converts digitak data to an analogue singal

- Data is encoded by modulating the amplitude of an analogue carrier signal
  Reason: less distortion on such a signal than alternatives

  Also uses phase modulation and multiple levels

- A tuplical dial up modem (V92) support up to 56 kpbs

# Multiplexing

Time division multiplexing:

- Alternate between multiple channels
  Synchronous
  Fixed rate means errors don't propagate
  Baiscly like an analogue connection.

Multiplexer needs far higher data rate.
No signal sill uses bandwidth.

# Circuit switching

Path calculated from phone number.
Each switching office forwards the call to the destination.
When the other side answers, the system starts to behave as if a cable was connecting both.

Switching offices uses to be manual.

Latency: time travel in cable.
Physical failuer kills te connection.

Packet switching is different due to out of order, higher latency, less wasted potential, and robust behavoiour.

# Digital Subscriber lines

- most common broadband technlogy
- bandwidth ~3khz
- in city can reach >1mhz
- rates from 512kbps to 24mbps

# Discrete Multitone DMT encoding

- DSL dvides the bandwidth into 256 narrow channels
- Bottom channel for voice
- Other channels work like other normal modems.

*More channels helps avoid working around non-working frequencies, and bandwidth range.*

Limit of voice around 25 KHz because most communication doesn't require data at higher frequencies than 20 khz

# ADSL ans SDSL

# Assymetric DSL

- for home users
- most channel for downstream
- 8 mbps down, and mbps up

# Symmetric DSL

- designed for buisness
- equal up and down to
- *contention ratio* nomally lower (required to service clients)

Share less with other people, higher quality

# ADSL equipment

# Fibre to the X (FTT[CBHP])

Increases bandwidth of parts of the local loop

- FTTC (cabinet/curb) street cabinet less than 300m from premises
- FTTB (Building) basemencet of an appartement or lae business premises
- FTTH (Home) - inside user's homr or offce (fibber all the way to the house) // the future
- FTTP (Premises) can mean either FTTB or FTTH. (Do not confuse name with procotol)

