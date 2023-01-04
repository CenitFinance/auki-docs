# Vesting schedule

The simulation considers vesting schedules for some investors and for the treasury. 
Each simulation step, the amount vested since the last step is calculated and added to the corresponding balance.

All schedules follow the same formulae:

Cliff time -> $\Delta t_c$

Vesting time -> $\Delta t_v$

Total vesting amount -> $v_t$

Vesting start time -> $t_0$

$t < t_0 + \Delta t_c$
$$
v(t) = 0
$$
$t \ge t_0 + \Delta t_c ; t < t_0 + \Delta t_v$
$$
v(t) = \frac{v_t \cdot \Delta t_v}{t - t_0}
$$
$t \ge t_0 + \Delta t_v$
$$
v(t) = v_t
$$

Taking this into account, the vested amount in each step is calculated by integration from the last step to the current one:

$$
V(t) = \int v(t) dt
$$
