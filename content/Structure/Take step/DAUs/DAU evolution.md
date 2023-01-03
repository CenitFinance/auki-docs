## Grow and stagnate

In this model, the DAUs grow with a base rate at the beginning and steadily reduce their growth until they asymptotically approach the DAUs at saturation value

Saturation time -> $d_s$

Base DAUs acquisition per second -> $b$

Initial DAUs -> $U_0$

DAUs at saturation -> $U_s$

Saturation factor:

$$
s = \frac{U_s - bt_s - U_0}{t_s^2}
$$

DAUs at time t:

$$
U(t) = st^2 + bt + U_0
$$

## Grow, peak and decrease

In this model the DAUs grow until they reach a peak and then gradually decline

Initial DAUs -> $U_0$

DAUs at peak -> $U_p$

Final DAUs -> $U_f$

Peak time -> $t_p$

Time to decrease -> $t_d$

$t < t_p$

$$
U(t) = \frac{U_0 \left(U_p - U_0\right)  \left[1 - \cos\left(\frac{t}{t_p}\pi\right)\right]}{2}
$$

$t > t_p ; t < t_p + t_d$

$$
U(t) = \frac{U_p - (U_p - U_f) * \left[1 - \cos\left(\frac{t - t_p}{t_d}\pi\right)\right]}{2}
$$
$t \geq t_p + t_d$

$$
U(t) = U_f
$$

