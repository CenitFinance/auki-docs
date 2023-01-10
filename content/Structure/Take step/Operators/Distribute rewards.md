# Distribute rewards

The amount of tokens minted in an epoch is distributed to the treasury and the operators. 
The ratio of the tokens that go to the operators is determined by the Hagall rewards ratio design parameter.

An additional ammount might go to the operators from the treasury as incentives, intended to encourage new participants to join the network.
For the purposes of the simulation, this option is activated whenever the number of operators is below a threshold number of concurrent sessions per worker, in order to avoid the network reaching a state where there are not enought operators to serve all the traffic.

## Calculation

The amount delivered to the treasury is:

$$
D_t = M \cdot (1 - r_o)
$$

where
 * $D_t$ is the amount of tokens delivered to the treasury
 * $M$ is the amount of tokens minted in the epoch
 * $r_o$ is the Hagall operators rewards ratio

From that amount, the treasury might decide to deliver extra incentives towards the operators:

$$
D_i = r_i \cdot D_t
$$

where
 * $D_i$ is the amount of tokens delivered to the operators as incentives
 * $r_i$ is the Hagall incentives ratio

The $r_i$ parameter is calculated as follows in the simulation:

$$
r_i = \max \left(0, \min \left( r_{i, max}, r_{i, max} \cdot \dfrac{S_w - S_{w, threshold}}{S_{w, maxincentives} - S_{w, threshold}}  \right) \right)
$$

where
 * $r_i$ is the Hagall incentives ratio
 * $r_{i, max}$ is the Hagall incentives ratio maximum
 * $S_w$ is the current number of concurrent sessions per worker
 * $S_{w, threshold}$ is the minimum number of concurrent sessions per worker at which incentives are activated
 * $S_{w, maxincentives}$ is the number of concurrent sessions per worker at which incentives reach their maximum

Finally, the amount from which operator rewards will be calculated is:

$$
D_o = M \cdot r_o + D_i
$$

where
 * $D_o$ is the amount of tokens delivered to the operators
 * $D_i$ is the amount of tokens delivered to the operators as additional incentives from the treasury
 * $r_o$ is the Hagall operators rewards ratio

Rewards are distributed to the operators according to their participation in the network and the service they provided.

The amount of tokens delivered to each operator are divided between service and participation rewards:

$$
D_{o, i} = D_o \cdot \left(\dfrac{T_{o, i}}{T_o} \cdot r_{o, service} + \dfrac{1}{N} \cdot (1- r_{o, service})  \right)
$$

where
 * $D_{o, i}$ is the amount of tokens delivered to operator $i$
 * $D_o$ is the amount of tokens delivered to the operators
 * $T_{o, i}$ is the traffic served by operator $i$
 * $T_o$ is the total traffic served by all the operators
 * $N$ is the number of operators
 * $r_{o, service}$ is the Hagall operators rewards ratio for service (as opposed to participation)
