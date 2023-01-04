# Mint tokens

Every minting epoch (e.g. one day), the contract mints an amount of tokens that may depend on the total amount of tokens burnt since the previous minting epoch.

This behaviour, including the length of the epoch, is part of the design of the tokenomics, and has been parameterized in various design parameters. There are multiple minting options in the simulation to choose from, defined below.

## Constant deflation rate

Burnt tokens since last minting -> $B$

Deflation rate -> $r$

Minting
$$
M(B) = r B
$$

## Asymptotic mint rate (reused formula)

Current value -> $v$

Crosspoint value -> $v_c$

Initial minting rate -> $r_0$

Final minting rate -> $r_f$

Value ratio -> $v_r(v) = \frac{v}{v_c}$

$$
r(v) = \frac{v_r(v)}{1 + v_r(v)} (r_f - r_0) + r_0
$$

## Market cap dependent deflation rate

Burnt tokens since last minting -> $B$

Market cap crosspoint -> $C_c$

Initial mint ratio -> $m_0$

Final mint ratio -> $m_f$

Asymptotic mint rate where $v = C$, $v_c = C_c$, $r_0 = m_0$ and $r_f = m_f$

Mintrate
$$
M(C,B) = r(C)\cdot B
$$

## Burnt tokens dependent deflation rate

Burnt tokens since last minting -> $B$

Burnt tokens crosspoint -> $B_c$

Initial mint ratio -> $m_0$

Final mint ratio -> $m_f$

Asymptotic mint rate where $v = B$, $v_c = B_c$, $r_0 = m_0$ and $r_f = m_f$

Minting
$$
M(B) = r(B) \cdot B
$$

## Time dependent deflation rate

Burnt tokens since last minting -> $B$

Time crosspoint -> $t_c$

Initial mint ratio -> $m_0$

Final mint ratio -> $m_f$

Asymptotic mint rate where $v = t$, $v_c = t_c$, $r_0 = m_0$ and $r_f = m_f$

Minting
$$
M(t,B) = r(t) \cdot B
$$

## Time dependent mint rate

Time crosspoint -> $t_c$

Initial mint rate -> $M_0$

Final mint rate -> $M_f$

Asymptotic mint rate where $v=t$, $v_c = t_c$, $r_0 = M_0$ and $r_f = M_f$

Minting
$$
M(t) = r(t)
$$

## Constant mint rate

Mint rate -> $M$

Minting
$$
M(t) = M
$$

## Constant deflation rate with minimum

Minimum mint rate -> $M$

Burnt tokens since last minting -> $B$

Deflation rate -> $r$

Minting
$$
M(B) = \max \{M, rB\}
$$

## Split minting calculator

Minting calculators -> $\{M_i\}$

Starting times -> $\{t_i\}$

Minting calculator contribution
- $t > t_i ; t < t_{i+1}$
	- $c_i = 1$
- else
	- $c_i = 0$

Minting calculator
$$
M = \sum c_iM_i
$$

## Changing minting calculator

Minting calculators -> $\{M_i\}$

Starting times -> $\{t_i\}$

Relaxation time -> $\Delta t_r$

Minting calculator contribution

- $t > t_{i-i}; t < t_i; t > t_i - \Delta t_r$
	- $c_i = \frac{t_i - t}{\Delta t_r}$
- $t > t_t;t > t_{i+1} - \Delta t_r$
	- $c_i=\frac{t-(t_{i+1}-\Delta t_r)}{\Delta t_r}$
- $t > t_i;t<t_{i+1}-\Delta t_r$
	- $c_i=1$
- else
	- $c_i=0$

Minting calculator
$$
M = \sum c_iM_i
$$
