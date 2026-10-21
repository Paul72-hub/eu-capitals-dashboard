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

5)je dirais Madrid quelque chose comme ça

> **Reflection — was your prediction right?** Compare the real top-ranked capital
> to what you predicted in Stage 3. If they match, what does that tell you about how
> well you understood the 50/50 formula? If they don't match, what surprised you —
> was it the weather data, the distance, or the formula itself?

6) C'est bien en accord avec ce que j'avais dis

> **Reflection — monitoring (CM4):** GitHub automatically disables a scheduled
> workflow after 60 days with no repository activity — a real, documented behavior,
> not a bug. If this dashboard's schedule silently stopped running (or started
> silently failing every week), what is the *one* thing on the live public page a
> visitor could look at to notice something was wrong, without checking the Actions
> tab? Is that signal good enough on its own, or would you add something?

7) Le signal visible sur la page est la ligne en bas : « Data last updated 2026-10-21T… ». Si le workflow s'arrête, cette date cesse d'avancer. Un visiteur qui voit une date vieille de plusieurs semaines peut comprendre que les données ne sont plus à jour.
De plus il est tout petit, pas visible en gris
On pourrait ajouter une alerte si les datas n'ont pas été update depuis plus de 7 jours.

> **Reflection — the unguided step:** which file(s) did you change, and why were
> those the right place(s) to change? And separately: is the "best" destination an
> absolute fact about these 26 capitals, or does it depend on where you start from?
> Compare your own top result to a classmate's (different origin city) if you can —
> did you get the same recommended capital?

8) scripts/fetch_and_score.py : c'est là que la ville de départ est définie, avec les coordonnées et l'exclusion. Elle intervient dans le calcul de la distance, donc du CO₂ et du score final. docs/index.html : le nom « Paris » était écrit en dur dans le texte affiché. Plutôt que de le remplacer à la main, le script écrit maintenant "origin" dans rankings.json et la page le lit. Le nom de la ville n'est donc défini qu'à un seul endroit. Si on change d'origine, il suffit de modifier le script, et la page suit automatiquement.
Partie 2 : la « meilleure » destination est-elle absolue ?
Non, elle dépend du point de départ :
Le score final n'est donc pas une propriété de la ville. C'est une mesure relative, qui dépend de l'utilisateur et de son point de départ.
Capitale gagnante est la même mais la deuxième a changé
