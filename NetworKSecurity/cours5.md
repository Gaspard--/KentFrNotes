# Mobile Telephone Networks

Several generations:
 - 1G: analogue voice (1984, obsolete)
 - 2G: digital (1991, still widely deployed)
 - 3G: digital voice, multimedia and data (2002)
 - Pre-4G: high-speed mobile broadband (2010)
 - 4G: LTE Advanced / WiMAX-Advanced (comming out)
 - 5G: LTE Advanced Pro

Region devided in cells, each centre is a *base station*.
Cellular structure allows more frequency band reuse.
Since phones are closer to base stations, power consumptions is reduce.
Base stations connect directly to switching offices.

## 2G & 2.5G

Bandwidth is split into hundreds of narrow channels, each capable of carrying several telephone callls.


### GPRS (General Packet Radio Service)
  - packet switched sevice overlaying 2G
  - special message to alloocat channel and time for transmission
  -> 44 kbps
### EDGE:
  - faster bps per channel
  - boosts GPRS to 384 kbps

## 3G

- global standart
- UMTS (Universal Mobile Telecommuications System) aka W-CMDA (Wideband CDMA)


- Maximum data rate depends on speed of user
  - stationary: 2000 kbps
  - walking : 384 kbps
  - driving a car : 144 kbps

-> slowdown due to handover (crossing of cells)

# CMDA:

a bit lke different users using different languages
works based on vetor algebra, uses vector base.

- All devices use entire bandwidth.
- Each transmitter has a unique chip sequence

Vector count higher than dimension count, values calculated statisticly.

## Enchance 3G

- HSDPA
 - uses shared channels with modified from of CDMA
- HSUPA
 - similar to HSDPA but inverted
- HSPA+
 - uses MIMO (multiple is, multiple out)
 - multiple channels per wavelength. Uses multiple attenas

## LTE: 3G partnership project Long Term Evolution - release 8/9

- A pre-4G tehcnology but marketed as 4G or 4G LTE!
- Better performance but not true 4G
- Key characteristics
 - uses Orthogonal Frequency-division Multiple Access (OFDMA) instead of CDMA.
 - copes better with fast motion than 3G.
 - supports full IP operator (hybrid between mobile network)
 - uses different radio bands to 3G (not compatible)
 - preformance has gone up since 2010 and keeps increasing

Data rates:
(down / up)
- cat 1 : 10mbps / 5mbps (worse tthan 3G)
- cat 2 : 50mbps / 25mbps
- cat 3 : 100mbps / 50mbps
- cat 4 : 150mbps / 50mbps
- cat 5 : 300mbps / 75mbps

# True 4G

- Tehcnologies that meet the minimum requirements for 4G specified by the international standarts body are referred to as "True 4G"
- True 4G offers 1 Gbps to walking, and 100 Mbps to users travelling at speed in cars and trains (required by standart)
- Primarly data service (although low-latency networks may still be available and used)
- Two true 4G technologies:
 - LTE-A (advanced)
  - Builds on LTE
 - Mobile WiMax

## LTE Advanced

- Backward compatible
- Uses better mimo, carrier aggregation
- CoMP techniques improve perfomance at cell edges, mobiles can use multiple stations a once

Data rates:
- cat 6 : 300mbps / 50mbps
- cat 7 : 300mbps / 100mbps
- cat 8 : 1200mbps / 1500mbps (cell)
- cat 8 : 3000mbps / 600mbps (single user)

## LTE Advanced PRO

- specification still under development
- aims to create universal wireless communication systel fir a wide range of devices, platforms and applications
- objectives:
 - 100% coverage of the earth
 - boost peak data rate of 10 Gbps
 - reduce end-to-end latency of 1ms
 - reduce power consumption by 90%
 - support 10x-100x as many connected devices
- Full implementation not expected until about 2020 (but features may begin appearng soon)