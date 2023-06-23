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
		- You also can't put in too much mana, or the SOUL you're attempting to add will just ![[Determination.gif]]
		- I'm going to say this is where the Stokoff constant, $k_S$, comes in
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

So, let's try and put all this together:

Calculating $M_I$ involves the following variables:
- $n$, the number of SOULS
- $F_S$, the force of attraction between SOULS
	- Depends on $n$
- For inanimate vessels:
	- $F_V$, the force of attraction between the ÜBERSOUL and the vessel
		- Inversely proportional to $n$
		- Inversely proportional to $V_C$, the volume of the container
- For living vessels:
	- $F_C$, the force of attraction between the BÜBERSOUL and the container
		- Inversely proportional to $n$
		- Inversely proportional to $V_C$, the volume of the container
	- $F_H$, the force of attraction between the BÜBERSOUL and the host
		- Inversely proportional to $d^2$, the distance between the container and the host
		- Proportional to $n$

and the following constants:
- $L_E$, the Ejiofor limit
- $k_E$, Ejiofor's constant
- $e$, Euler's number

$M_C$ is similar, but additionally involves:
- $\sum m_i$, the initial Mana added to each SOUL
	- Depends on $n$
- $k_S$, Stokoff's constant

and does not depend on $L_E$.

For inanimate vessels:
$$
M_I = \frac{L_E}{2} F_S F_V
$$
$$
F_S = 
$$