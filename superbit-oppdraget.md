# super:bit-oppdraget

Disse oppgavene er basert på oppgavene i [super:bit-oppdraget](https://www.vitensenter.no/superbit/laerer/superbit-oppdraget/). Oppgavene er tilrettelagt for synshemmede elever og bruker tekstprogrammering med Python i Visual Studio Code i stedet for blokkbasert programmering i MakeCode. Disse tilrettelagte oppgavene bruker lyd i stedet for visuell output på micro:bit-skjermen.

## Kom i gang med micro:bit

Målet med øvelsen er å lage enkle programmer i Python og laste dem ned til micro:bit. 

### Oppgave: Spill en melodi

I denne oppgaven skal du programmere micro:bit slik at den spiller melodier.

<details>
<summary>Klikk for å utvide.</summary>
&nbsp;

**NB!** Vær varsom med å bruke hodetelefoner når du bruker micro:bit med lyd (musikk eller syntetisk tale). Lydnivået kan være uforutsigbart.

Utstyr: micro:bit, høyttalere, ledninger, Visual Studio Code.

#### Deloppgave A

Først skal du lage et program som spiller en melodi.

1. Opprett en ny fil (**Ctrl+N**).
2. Lagre filen (**Ctrl+S**). Gi filen et navn i feltet Filnavn og velg Python i feltet Filtype. (Eller skriv hele filnavnet direkte i feltet Filnavn, for eksempel melodi.py.) Alle Python-filer skal ha etternavnet .py. Da vet Visual Studio Code at du programmerer i Python.
3. Når du programmerer micro:bit, må programmet alltid starte med at du gjør micro:bit-modulene tilgjengelig for programmet ditt. Disse modulene er en slags verktøykasse med det meste du trenger for å programmere micro:bit:

```
from microbit import *
```

4. Og for at micro:bit skal kunne spille en melodi, trenger du å importere music-modulen også. Vi må skrive denne import-setningen litt annerledes enn den forrige:

```
import music
```

5. Nå skal du skrive instruksjonen som gjør at micro:bit spiller melodien Happy birthday. Legg merke til at du må skrive navnet på melodien med store bokstaver (BIRTHDAY). Happy birthday er en av omtrent 20 melodier som følger med micro:bit. La det gjerne være en blank linje mellom import-setningene og resten av programmet.

```
music.play(music.BIRTHDAY)
```

6. Lagre endringene du har gjort i programmet (**Ctrl+S**). Programmet ditt skal nå se slik ut:

```
from microbit import *
import music

music.play(music.BIRTHDAY)
```

7. Sørg for at micro:bit er koblet til PC-en med USB-kabelen som følger med.
8. Overfør programmet ditt til micro:bit med kommandoen **Ctrl+F5**. Når overføringen er ferdig etter noen få sekunder, vil micro:bit kjøre programmet. Du vil da høre melodien i høyttaleren.
9. Hvis du vil høre melodien en gang til, må du trykke på reset-knappen på baksiden av micro:bit. Da kjøres programmet på nytt.

#### Deloppgave B

Nå skal du utvide programmet ditt slik at det spiller to melodier etter hverandre i det uendelige.

1. Gå tilbake til programmet ditt (om nødvendig bruk **Ctrl+1**).
2. Finn tilbake til det stedet der du spilte av melodien BIRTHDAY. Lag en ny linje etter denne og skriv en tilsvarende linje. Men i stedet for BIRTHDAY skal du velge en melodi som heter POWER_UP.
3. Nå vil programmet spille to melodier etter hverandre. Men for at melodiene skal spilles uendelig antall ganger, trenger du en løkke. I Python kan du lage en evig løkke ved å skrive while True etterfulgt av kolon.

    while-løkka må komme foran alle instruksjonene som skal høre til løkka. Instruksjonene som skal utføres et uendelig antall ganger, må da komme på ny linje med innrykk:

```
while True:
    music.play(music.BIRTHDAY)
    music.play(music.POWER_UP)
```

4. Lagre endringene du har gjort i programmet (**Ctrl+S**). Programmet ditt skal nå se omtrent slik ut:

```
from microbit import *
import music

while True:
    music.play(music.BIRTHDAY)
    music.play(music.POWER_UP)
```

5. Overfør programmet ditt til micro:bit med kommandoen **Ctrl+F5**.
6. Hva skjedde denne gangen?
7. Når du bruker en slik while-løkke vil programmet kjøre helt til du overfører et nytt program.

</details>
&nbsp;

### Oppgave: Trykk på knappene og hør en tekst bli lest opp

micro:bit har to knapper på forsiden, A og B. Nå skal du bruke disse knappene til å få micro:bit til å lese høyt med syntetisk tale. Talesyntesen i micro:bit er bare på engelsk.

<details>
<summary>Klikk for å utvide.</summary>
&nbsp;

Utstyr: micro:bit, høyttalere, ledninger, Visual Studio Code.

#### Deloppgave A

I denne oppgaven skal du programmere micro:bit slik at den leser opp en setning når du trykker knapp A.

1. Opprett en ny fil (**Ctrl+N**).
2. Lagre filen med et passende navn (**Ctrl+S**). Husk filetternavn .py.
3. Akkurat som i forrige oppgave, må vi starte med å importere micro:bit-modulene:

```
from microbit import *
```

4. For at micro:bit skal kunne bruke syntetisk tale, må du importere speech-modulen også:

```
import speech
```

5. Etter disse to import-setningene, må du ha en while-løkke. Løkka gjør at programmet aldri stopper. Vi kan tenke oss at programmet kjører og kjører mens det følger med på hva du velger å gjøre. Hvis du trykker på knappen A, vil programmet være klar til å utføre de instruksjonene som du har valgt at knapp A skal utføre.

```

while True:
```

6. Husk at de instruksjonene som skal høre til while-løkka, må skrives på ny linje og ha innrykk.

7. Det neste du skal gjøre, er å bestemme hva som skal skje når knapp A trykkes. Vi trenger en if-setning. En if-setning består av ordet if etterfulgt av en betingelse eller et vilkår. Betingelsen avgjør om instruksjonene som hører til if-setningen skal utføres eller ikke. Hvis betingelsen er sann, vil instruksjonene utføres. Betingelsen du skal bruke her er om knapp A blir trykket eller ikke. Dette kan du skrive slik:

```
if button_a.is_pressed():
```

8. Nå har du nesten alt på plass. Det siste du trenger er selve instruksjonen som leser opp en setning med den syntetiske talen. Akkurat som med while-løkka, må alle instruksjonene som skal høre til if-setningen ha innrykk. Det som hører til while-løkka fikk ett innrykk. Det som hører til if-setningen får enda en innrykk.

    Du må bruke en funksjon som hører til modulen speech. Funksjonen heter say(). Inne i parentesen skriver du setningen som skal leses opp omgitt av anførselstegn, for eksempel setningen "Hello world, how are you?". Siden funksjonen say hører til modulen speech, må du skrive speech og et punktum foran say:

```
speech.say("Hello world, how are you?")
```

9. Lagre endringene i programmet ditt (**Ctrl+S**). Programmet skal nå se omtrent slik ut:

```
from microbit import *
import speech

while True:
    if button_a.is_pressed():
        speech.say("Hello world, how are you?")
```

10. Overfør programmet ditt til micro:bit med kommandoen **Ctrl+F5**.
11. Hva skjer hvis du trykker på knapp A? Hva skjer hvis du trykker på knapp B? Eller hva skjer hvis du ikke trykker på noen av knappene?

#### Deloppgave B

Nå skal du programmere micro:bit slik at den leser opp en annen setning når du trykker knapp B. Da vil du få et program som leser én setning for knapp A og en annen for knapp B. Gjør endringer i programmet fra deloppgave A slik at du får til dette.

Tips: du trenger to if-setninger etter hverandre. Den ene sjekker om knapp A blir trykket og den andre sjekker om knapp B blir trykket. Når du  bruker to if-setninger, skrives de på en litt spesiell måte. Den første heter bare if (akkurat som i forrige oppgave). Men den neste heter elif (som betyr else if). Dette er en skisse av koden du trenger:

```
if button_a.is_pressed():
    leser en setning
elif button_b.is_pressed():
    leser en annen setning
```

1. Fullfør programmet og lagre det.
2. Overfør programmet til micro:bit med kommandoen **Ctrl+F5**.
3. Hva skjer nå når du trykker på knapp A og knapp B?

</details>
&nbsp;

### Oppgave: Ikke rist meg!

micro:bit har et akselerometer som kan registrere endring i bevegelse og risting. Et akselerometer er det samme som en bevegelsessensor. Kan du få micro:bit til å si ouch! (au!) når noen rister på den?

<details>
<summary>Klikk for å utvide.</summary>
&nbsp;

Utstyr: micro:bit, høyttalere, ledninger, Visual Studio Code.

1. Opprett en ny fil (**Ctrl+N**).
2. Lagre filen med et passende navn (**Ctrl+S**). Husk filetternavn .py.
3. Denne oppgaven ligner mye på deloppgave A i forrige oppgave. Du trenger micro:bit-modulen og speech-modulen, en while-løkke og en if-setning. Og så skal du få micro:bit til å si "Ouch!". Men i stedet for at micro:bit skal si noe når du trykker knapp A, skal du få micro:bit til å si noe når du rister den.
4. For å finne ut om micro:bit ristes, trenger du en ny modul som kalles accelerometer. Den er en del av micro:bit-modulen så du trenger ikke importere den. Accelerometer har en funksjon som kalles was_gesture() og det er den som sjekker om micro:bit ristes. Du kan bruke dette i en if-setning slik:

```
if accelerometer.was_gesture("shake"):
```

5. Fullfør programmet på samme måte som du gjorde i forrige oppgave. Husk innrykk!
6. Overfør programmet ditt til micro:bit med kommandoen **Ctrl+F5**.
7. Hva skjer når du rister micro:bit?

</details>
&nbsp;

---

## Kjør en meter med Bit:bot

I denne oppgaven skal du programmere roboten Bit:bot. Roboten skal starte når man trykker på knapp A. Den skal kjøre frem 1 meter, snu 180 grader og kjøre tilbake igjen.

<details>
<summary>Klikk for å utvide.</summary>
&nbsp;

Utstyr: micro:bit, Bit:bot XL, Visual Studio Code.

### Deloppgave A

I første deloppgave skal du programmere roboten slik at den kjører én meter rett fram.

1. Lag en ny fil (**Ctrl+N**) i Visual Studio Code.
2. Lagre filen (**Ctrl+S**).
3. I tillegg til den vanlige import-setningen for micro:bit, trenger du en import-setning for modulen som inneholder Bit:bot-funksjonene:

```
from microbit import *
from bitbot import *
```

4. For å få roboten til å kjøre rett fram, kan du bruke en funksjon fra bitbot-modulen som heter goms() (go milliseconds). goms krever at du oppgir 3 såkalte argumenter, nemlig retning (FORWARD eller REVERSE), hastighet (0-100%) og tid (antall millisekunder). Argumenter er informasjon som funksjonen trenger for å gjøre det den skal. Det kan være lurt å velge en ikke altfor høy hastighet, for eksempel 30.

    Når du skal bruke funksjonene som hører til Bit:bot, starter du instruksjonene med bitbot etterfulgt av punktum. Deretter kommer selve funksjonen:

```
bitbot.goms(FORWARD, 30, <millisekunder>)
```

5. Hvilken verdi må du sette inn i stedet for millisekunder for at roboten skal gå én meter rett fram? Verdien skal altså oppgis i millisekunder. Hvor mye er det?
6. Valgfritt: Det går an å programmere roboten slik at den lager pipesignaler. Du kan for eksempel få den til å pipe når den er ferdig med å kjøre. Erstatt millisekunder i koden under med antall millisekunder du vil at den skal pipe:

```
bitbot.buzz(<millisekunder>)
```

7. Lagre programmet ditt, koble til micro:bit og overfør med **Ctrl+F5**.
8. Pass på at roboten er avslått. Koble USB-ledningen fra micro:bit og sett den inn i sporet på roboten slik at de to knappene (A og B) vender framover.
9. Sett roboten på gulvet og slå den på med bryteren på baksiden. (Trykk på reset-knappen på baksiden av micro:bit, hvis roboten ikke starter automatisk.)
10. Hvor langt kjørte roboten? For kort eller for langt? Hva må du gjøre for å få roboten til å komme nærmere en meter?

### Deloppgave B

I denne deloppgaven skal du endre litt på programmet ditt slik at roboten ikke kjører før du trykker på knapp A.

**Tips!** Bruk det du har lært om if-setninger til å løse oppgaven. Du trenger også en while-løkke.

### Deloppgave C

I denne siste deloppgaven skal du bygge videre på programmet ditt. Etter at Bit:bot har kjørt én meter rett fram, skal den snu 180 grader og kjøre tilbake til utgangspunktet.

1. Modulen bitbot har en funksjon som kalles spinms() (spin milliseconds). Den kan du bruke når du skal snu roboten. spinms() krever 3 argumenter, nemlig retning (RIGHT eller LEFT), hastighet (0-100%) og tid (antall millisekunder). Du må da skrive:

```
bitbot.spinms(<retning>, 30, <millisekunder>)
```

2. Vi kan beholde samme hastighet som før. Hvilken verdier vil du sette inn for retning og millisekunder i koden din?
3. Når roboten har snudd 180 grader, skal den kjøre rett fram tilbake til utgangspunktet. Funksjonen for å kjøre rett fram har du brukt tidligere (goms). Hvordan må du skrive instruksjonen denne gang?
4. Lagre programmet ditt.
5. Slå av roboten og koble fra micro:bit. Koble USB-kabelen til micro:bit og overfør programmet med **Ctrl+F5**.
6. Koble USB-kabelen fra micro:bit og sett micro:bit inn i roboten igjen.
7. Plasser roboten på gulvet og slå den på med bryteren på baksiden.
8. Hva gjorde roboten da den skulle snu 180 grader? Kom den tilbake til utgangspunktet? Hvis ikke, hvilke endringer må du gjøre i programmet ditt?

</details>
&nbsp;

---

## Kjør ei løype med BitBot
   
I den forrige oppgaven programmerte du roboten til å kjøre én meter fremover, snu 180 grader og kjøre tilbake. I denne oppgaven skal du få roboten til å kjøre fra start til mål på en vei på gulvet. Kan du bruke noe av det du lærte tidligere i denne oppgaven?

<details>
<summary>Klikk for å utvide.</summary>
&nbsp;

![Bane på gulvet laget med elektrikertape](https://github.com/oivron/komme-i-gang-microbit/blob/master/img/vei-med-elektrikertape.jpg)
    
Utstyr: micro:bit, Bit:bot XL, Visual Studio Code, sort elektrikertape.

1. Lag en ny fil (**Ctrl+N**) i Visual Studio Code.
2. Lagre filen (**Ctrl+S**).
3. Valgfritt: Sett inn pipesignaler der du vil i programmet ditt, for eksempel når roboten starter, svinger eller stopper.
4. Du trenger den vanlige import-setningen for micro:bit og import-setning for bitbot-modulen:

```
from microbit import *
from bitbot import *
```
5. Bruk det du har lært i forrige oppgave til å kjøre roboten langs veien fra start til mål.
6. Lagre endringer i programmet ditt.
7. Slå av roboten og sett micro:bit inn i roboten. Koble USB-kabelen til micro:bit og overfør programmet med **Ctrl+F5**.
8. Koble USB-kabelen fra micro:bit. Sett roboten på gulvet der veien starter. Slå på roboten med bryteren på baksiden.
9. Klarte roboten å følge veien fra start til mål? Gjør nødvendige endringer hvis roboten ikke fulgte veien fra start til mål.
</details>
