# Etter super:bit-oppdraget

Disse oppgavene er basert på oppgavene fra [Etter super:bit-oppdraget](https://www.vitensenter.no/superbit/elev/etter-superbit-oppdraget/). Oppgavene er tilrettelagt for synshemmede elever og bruker tekstprogrammering med Python i Visual Studio Code i stedet for blokkbasert programmering i MakeCode.

## Lag en selvkjørende bil

I denne oppgaven skal du programmere Bit:Bot til å bruke linjesensorene for å kjøre på en svart linje. Du kan kjøre roboten på super:bit-matta eller på en kjørebane du har laget selv.

<details>
<summary>Klikk for å utvide.</summary>

Utstyr: micro:bit, Bit:bot XL, Visual Studio Code. I tillegg trenger du en super:bit-matte eller en kjørebane laget med elektrikertape.

BitBot har to linjesensorer. Hver av dem har en liten sender og mottaker som sender ut og mottar usynlig infrarødt lys. Dersom lyset treffer den svarte linja, så absorberes den, noe mottakeren registrer ved at linjesensoren sender tallet 1. Dersom lyset treffer den lyse delen av underlaget, sender linjesensoren tallet 0.

Når den svarte linja er midt mellom de to sensorene, skal roboten kjøre rett fram. Når roboten kommer til en venstresving, dekker linja for lyset fra venstre sensor. Da vil vi at roboten skal kjøre mot venstre.
Når roboten kommer til en høyresving, dekker linja for lyset fra høyre sensor. Da vil vi at roboten skal kjøre mot høyre.

1. Opprett en ny fil (**Ctrl+N**).
2. Lagre filen (**Ctrl+S**) i Visual Studio Code.
3. Du trenger den vanlige import-setningen for micro:bit og import-setning for bitbot-modulen:

```
from microbit import *
from bitbot import *
```

4. Som i tidligere oppgaver trenger vi en evig løkke:

```
while True:
```

5. Her er det viktig at vi passer på hvor kjørebanen går. Programmet ditt må følge med på om veien svinger, enten til venstre eller til høyre. Det kan du gjøre ved å følge med på om tallet som linjesensorene sender er 0 eller 1. Hvis en av linjesensorene sender tallet 1, vet du at sensoren har kommet over den svarte linja. Da må du justere retningen slik at roboten svinger i den retningen som veien svinger.

    Du kan sjekke om høyre linjesensor sender tallet 1 ved å bruke funksjonen linesensor() i bitbot-modulen. Hvis tallet er 1, må du svinge roboten litt mot høyre. Hvilken instruksjon vil du bruke i stedet for "Sving roboten litt mot høyre"?

```
if (bitbot.linesensor(RIGHT) == 1):
    Sving roboten litt mot høyre
```

6. På samme måte kan du sjekke om venstre linjesensor sender tallet 1. Da kan du bruke en elif-setning:

```
elif (bitbot.linesensor(LEFT) == 1):
    Sving roboten litt mot venstre
```

7. Så langt har du programmert hva som skal skje hvis en av linjesensorene kommer inn på den svarte linja. Men hva skal roboten gjøre hvis ingen av sensorene sender tallet 1? Jo, det betyr at roboten bare skal fortsette å kjøre rett fram. Dette kan du få til ved å bruke en else-setning. En else-setning betyr at verken if eller elif slår ut. Hviken instruksjon vil du bruke i stedet for "Kjør roboten rett fram"?

```
else:
    Kjør roboten rett fram
```

8. Lagre endringene du har gjort i programmet (**Ctrl+S**).
9. Sørg for at roboten er avslått og sett micro:bit inn i roboten. Koble USB-kabelen til micro:bit og overfør programmet med **Ctrl+F5**.
10. Koble USB-kabelen fra micro:bit. Sett roboten på gulvet litt foran der kjørebanen starter. Slå på roboten med bryteren på baksiden.
