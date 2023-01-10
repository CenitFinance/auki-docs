# Centralized node management

It is assumed that AUKI Labs will maintain a certain number of centralized nodes in the network, and that the number of decentralized nodes will be adjusted to maintain a certain ratio of decentralized nodes to centralized nodes.

Therefore, at every time step where the number of decentralized nodes changes, the number of centralized nodes will be updated accordingly.

Additionally, at the TGE there is an initial base number of centralized nodes, which will be maintained throughout the simulation.

## Calculation

The desired number of centralized nodes is calculated as follows:

$$
N_{c, desired} = \dfrac{r_{c}}{1 - r_{c}} \cdot N_{d}
$$

where
 * $N_{c, desired}$ is the desired number of centralized nodes
 * $r_{c}$ is the desired ratio of centralized nodes to decentralized nodes
 * $N_{d}$ is the current number of decentralized nodes

To maintain the minimum number of centralized nodes, the desired number of centralized nodes is compared to the minimum number of centralized nodes:

$$
N_{c} = \max \left(N_{c, desired}, N_{c, min} \right)
$$

where
 * $N_{c}$ is the number of centralized nodes
 * $N_{c, desired}$ is the desired number of centralized nodes
 * $N_{c, min}$ is the minimum (initial) number of centralized nodes
