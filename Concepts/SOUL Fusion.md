---
alias: ÜBERSOUL, BÜBERSOUL
---
sudoChange:: MATH! And also lots of words.
Priority:: 1

- **SOUL Fusion** is the process by which two or more [[SOUL|SOULS]] are fused into a single unit, known as an ÜBERSOUL.
- An individual SOUL begins to lose integrity at [[Mana]] concentrations in excess of 121 TEj.
	- This is known as the Ejiofor limit, $L_E$
	- Some extremely powerful spells require more than 121 TEj of Mana
- An ÜBERSOUL can, of course, handle much more Mana than a typical SOUL
- However, unlike normal SOULS, there is a limit to how much Mana an ÜBERSOUL can withstand in its lifetime
	- This is proportional to the initial Mana cost of creating an ÜBERSOUL
		- What, you didn't think you could just do this for *free* did you?
		- Obviously, it requires less than 121 TEj. Otherwise, there would be no point.
		- Let's say the [[BLADE OF POWER]] does this for you (that's where the POWER comes from), but you can choose to add more Mana if you know what you're doing.
			- I'm going to say it adds 30 MEj, so around a 4th level spell.
		- You also can't put in too much mana, or the SOUL you're attempting to add will just ![[Determination.gif]]
		- I'm going to say this is where the Stokoff constant, $k_S$, comes in
		- The amount of Mana an exposed SOUL can withstand is significantly less than $L_E$. This limit was calculated by Rochelle Kohlenberg to be 19.389 GEj. Its symbol is $L_K$.
	- Normally, Mana is filtered through the body before coming into contact with the SOUL. This is partially why an ÜBERSOUL formed in a living vessel (also known as a Biologic ÜBERSOUL, or BÜBERSOUL) is more stable. It's also why the [[STAFF OF RULKOHIM]] is integral to the [[BFS 10000]]. ![[DIE ÜBERSEELE.png]]
- Both the instantaneous Mana maximum, $M_I$, and the cumulative Mana maximum, $M_C$, depend on the number of SOULS, $n$, comprising the ÜBERSOUL
	- More SOULS = stronger bonds = stronger ÜBERSOUL
	- This is known as the Power of Friendship ![[The Power of Friendship.png]]
		- It's actually named after the scientist who first theorized it, Paul Friendship. Ironically, he was a bitter old cunt, and he died alone.
		- This is where the Stokoff maximum applies. If $n>13$, the Power of Friendship becomes too strong, and the ÜBERSOUL implodes violently, not unlike a nuclear bomb.
- $M_I$ and $M_C$ also depend on whether the ÜBERSOUL was formed in a living vessel or an inanimate one.
	- Living vessel: Higher $M_I$, significantly higher $M_C$, can be formed from more SOULS, but must remain in close proximity to vessel
		- Obviously, SOULS tend to prefer being in living vessels, but they are only usable by the vessel itself in this state.
	- Inanimate vessel: Portable, requires fewer resources to make, but lower $M_I$ and $M_C$, and cannot contain as many SOULS
		- Paradoxically, the Mana costs of fusing more than 6 SOULS in an inanimate vessel exceeds the $M_C$ of the ÜBERSOUL.
- There is not only attraction between the constituent SOULS, $F_S$, but also between the ÜBERSOUL and its vessel, $F_V$.
	- Because a BÜBERSOUL must remain near its originating reactor (host), $F_V$ encompasses the attraction between the BÜBERSOUL and its container, $F_C$, as well as the attraction between the BÜBERSOUL and its host, $F_H$. $$F_{H} \propto \frac{1}{d^2}$$ where $d$ is distance between the BÜBERSOUL and the host.
		- (In our case, the host is [[Sam Ward|Sam]], and the container is [[CURSED AL'S CURSED ORB|THE ORB]].)

> L: What practical consequences do the attraction forces have? What happens when those forces are too low? Does a BÜBERSOUL need a minimal attraction force to its vessel to remain stable?

So, let's try and put all this together:

Calculating $M_I$ involves the following variables:
- $n$, the number of SOULS
- $F_S$, the force of attraction between SOULS
	- Depends on $n$
- For inanimate vessels:
	- $F_V$, the force of attraction between the ÜBERSOUL and the vessel
		- Proportional to $n$
		- Inversely proportional to $V_C$, the volume of the container
- For living vessels:
	- $F_C$, the force of attraction between the BÜBERSOUL and the container
		- Proportional to $n$
		- Inversely proportional to $V_C$, the volume of the container
	- $F_H$, the force of attraction between the BÜBERSOUL and the host
		- Inversely proportional to $d^2$, the distance between the container and the host squared
		- Proportional to $n$
		- Also depends on $\theta$, the angle between the BÜBERSOUL and the host

and the following constants:
- $L_E$, the Ejiofor limit
- $k_E$, Ejiofor's constant
- $e$, Euler's number
- $\pi$
- $\epsilon_0$, the permittivity of free space
- $c$, the speed of light

For inanimate vessels:
$$
F_S = \frac{e^{3n}}{k_E}
$$
$$
F_V = \frac{n}{V_C}
$$
$$
M_I = \frac{n \cdot L_E}{2} F_S F_V = \frac{n^2e^{3n}L_E}{2k_E V_C}
$$

For living vessels:
$$
F_S = \frac{e^{3n}}{k_E}
$$
$$
F_V = F_C \cdot F_H
$$
$$
F_C = \frac{n}{V_C}
$$
$$
F_H = \frac{n}{2\pi \epsilon_0 c d^2} \frac{\cos(\frac{\pi}{2}\cos\theta)}{\sin\theta}e^n
$$
$$
M_I = \frac{n^3 e^{4n} L_E \cos(\frac{\pi}{2}\cos\theta)}{4 k_E V_C \pi \epsilon_0 c d^2 \sin \theta}
$$

$M_C$ involves the following variables:
- $n$, the number of SOULS being added
- $F_S$, the force of attraction between SOULS
	- Depends on $n$
- For inanimate vessels:
	- $F_V$, the force of attraction between the ÜBERSOUL and the vessel
		- Proportional to $n$
		- Inversely proportional to $V_C$, the volume of the container
- For living vessels:
	- $F_C$, the force of attraction between the BÜBERSOUL and the container
		- Proportional to $n$
		- Inversely proportional to $V_C$, the volume of the container
	- $F_H$, the force of attraction between the BÜBERSOUL and the host
		- Inversely proportional to $d^2$, the distance between the container and the host squared
		- Proportional to $n$
		- Also depends on $\theta$, the angle between the BÜBERSOUL and the host
	- Possibly involves some other variable, $x$, that explains why $M_C$ is higher for living vessels
- $\sum m_i$, the initial Mana added to each SOUL
	- Depends on $n$
- $C$, the Mana cost of performing SOUL fusion (distinct from above)

And the following constants:
- $k_S$, Stokoff's constant

and does not depend on $L_E$.

%%
If "You also can't put in too much mana, or the SOUL you're attempting to add will just Determination.gif", then shouldn't $L_E$ be involved somehow? Maybe $L_E$ only applies when the SOUL is in the body, and there's a different, lower limit when the SOUL isn't contained somehow.

Heck, maybe $M_C$ is just $\ln(k_S - n) M_I$.
%%

```math-tex
# Constants
KE = 6.3459269958*10^-3 # Ejiofor's constant
LE = 121*10^12 # Ejiofor's limit
r = 0.2 # The radius of THE ORB in m
VC = (4 pi)/3 * r^3 # The volume of THE ORB
d = 1 # The distance from the vessel in m^3
KS = 39.810686024 # Stokoff's constant

# ÜBERSOUL M_I
n = 2
FS = e^(2n) * KE
FV = n / VC
MI = (n * LE) / 2 * FS * FV
MI / LE

# BÜBERSOUL M_I
FH = (n e^n)/(d^2)
BMI = MI * FH
BMI / LE

# M_C
log(KS - n) * MI
log(KS - n) * BMI
```

| $n$  | ÜBERSOUL($n$) $M_I$ | ÜBERSOUL($n$) $M_C$ | BÜBERSOUL($n$) $M_I$ | BÜBERSOUL($n$) $M_C$ |
|----|-----------------|----------------|------------------|------------------|
| 2  | 2.50 PEj        | 9.09 PEj       | 36.98 PEJ        | 134.32 PEJ       |
| 3  | 41.60 PEJ       | 150.00 PEj     | 2.51 EEj         | 9.04 EEj         |
| 4  | 546.45 PEj      | 1.96 EEj       | 119.34 EEj       | 427.03 EEj       |
| 5  | 6.31 EEj        | 22.40 EEj      | 4.68 ZEj         | 16.62 ZEj        |
| 6  | 67.13 EEj       | 235.35 EEj     | 162.49 ZEj       | 572.09 ZEj       |
| 7  | 675.14 EEJ      | 2.36 ZEj       | 5.18 YEj         | 18.09 YEj        |
| 8  | NaN             | NaN            | 155.39 YEj       | 537.60 YEj       |
| 9  | NaN             | NaN            | 4.44 REj         | 15.23 REj        |
| 10 | NaN             | NaN            | 122.44 REj       | 415.65 REj       |
| 11 | NaN             | NaN            | 3.27 QEj         | 11.00 QEj        |
| 12 | NaN             | NaN            | 85.35 QEj        | 283.83 QEj       |
| 13 | NaN             | NaN            | 2180 QEj         | 7170 QEj         |

#Concept/Soul/Soul-Fusion 