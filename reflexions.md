> **Reflection — before you build anything:** if you personally had to choose a
> destination, how would you weigh good weather against low CO₂? Would you ignore
> one of them entirely? Write 1-2 sentences now 

1) environ 60 % météo / 40 % CO₂, puisque visiter sous un mauvais temps ça gache l'expérience, et je préfère partir moins souvent
   mais qu'il fasse beau quand je parte.
   
> **Reflection — acquisition reliability:** before reading the docstring above a
> second time: why would making 26 separate API connections from the same script,
> in a loop, be *more* likely to fail than making 1 connection for all 26 capitals
> at once — not just slower, but more likely to actually fail? Write your guess,

2) Plus de chance d'avoir un problème de connexion sur 26 connexion que sur une seule
> **Reflection — provenance (CM3):** the CO₂ figure (0.15 kg CO₂e/km) is a rounded
> value from a real, cited range (0.12-0.15, DEFRA-style short-haul factors) that
> the script's own comment says to "verify/update." If this dashboard were going to
> be used by real travelers next year instead of graded once, what would you actually
> do about this number before publishing it?

3) Vérifier la source/Citer la source et puis prendre en compte les limites: les trajets courts peuvent se faire en train au lieu de l'avion par exemple

> **Reflection — relative vs. absolute:** `normalize()` finds the best and worst
> value *within this list of 26 capitals* and stretches everything between them to
> 0-1. If a 27th, unusually cold and rainy capital were added to the list, would a
> mediocre capital's real temperature change? Would its *score* change? What does
> that tell you about the difference between a measurement and a KPI built on top of
> it (CM2)?

4)  ça montre qu'il faut faire attention aux valeurs et qu'elle peuvent être biaisé, il faut un bon pré traitement

> **Reflection — predict, then check:** based on the personal weighting you wrote
> down at the very start of this TD, which capital do you *predict* will come out
> on top once you run this script for real? Write the city name and one sentence of
> reasoning now, before you run anything.
>

5)je dirais Athènes quelque chose comme ça
