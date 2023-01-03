For each actor, we have different vesting schedules, but they all follow the same formula

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

