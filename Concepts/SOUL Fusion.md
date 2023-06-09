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

and the following constants:
- $L_E$, the Ejiofor limit
- $k_E$, Ejiofor's constant
- $e$, Euler's number

For inanimate vessels:
$$
F_S = e^{2n}K_E
$$
$$
F_V = \frac{n}{V_C}
$$
$$
M_I = \frac{n L_E}{2} F_S F_V = \frac{ne^{2n}K_E}{2V_C}
$$

For living vessels:
$$
F_S = e^{2n}K_E
$$
$$
F_V = F_C \cdot F_H
$$
$$
F_C = \frac{n}{V_C}
$$
$$
F_H = \frac{ne^{n}}{d^2}
$$
$$
M_I = \frac{nL_E}{2} F_S F_C F_H = \frac{n^2e^{3n}K_E}{2 d^2 V_C}
$$

For both: $$M_C = \ln(K_S - n) M_I$$

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
| 2  | $2.50 \times 10^{15}$ Ej    | $9.09 \times 10^{15}$ Ej    | $36.98 \times 10^{15}$ Ej    | $134.32 \times 10^{15}$ Ej    |
| 3  | $41.60 \times 10^{15}$ Ej   | $150.00 \times 10^{15}$ Ej  | $2.51 \times 10^{18}$ Ej     | $9.04 \times 10^{18}$ Ej      |
| 4  | $546.45 \times 10^{15}$ Ej  | $1.96 \times 10^{18}$ Ej    | $119.34 \times 10^{18}$ Ej   | $427.03 \times 10^{18}$ Ej    |
| 5  | $6.31 \times 10^{18}$ Ej    | $22.40 \times 10^{18}$ Ej   | $4.68 \times 10^{21}$ Ej     | $16.62 \times 10^{21}$ Ej     |
| 6  | $67.13 \times 10^{18}$ Ej   | $235.35 \times 10^{18}$ Ej  | $162.49 \times 10^{21}$ Ej   | $572.09 \times 10^{21}$ Ej    |
| 7  | $675.14 \times 10^{18}$ Ej  | $2.36 \times 10^{21}$ Ej    | $5.18 \times 10^{24}$ Ej     | $18.09 \times 10^{24}$ Ej     |
| 8  | NaN             | NaN            | $155.39 \times 10^{24}$ Ej   | $537.60 \times 10^{24}$ Ej    |
| 9  | NaN             | NaN            | $4.44 \times 10^{27}$ Ej     | $15.23 \times 10^{27}$ Ej     |
| 10 | NaN             | NaN            | $122.44 \times 10^{27}$ Ej   | $415.65 \times 10^{27}$ Ej    |
| 11 | NaN             | NaN            | $3.27 \times 10^{30}$ Ej     | $11.00 \times 10^{30}$ Ej     |
| 12 | NaN             | NaN            | $85.35 \times 10^{30}$ Ej    | $283.83 \times 10^{30}$ Ej    |
| 13 | NaN             | NaN            | $2.18 \times 10^{33}$ Ej     | $7.17 \times 10^{33}$ Ej      |

#Concept/Soul/Soul-Fusion 