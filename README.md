# Neuroevolution
Tilførsel med genetisk algoritme til neuralt netværk


For at lave den genetiske algoritme, har vi delt det op i en fitness-funktion, reproduktions-funktion og en muterings-funktion. 

I fitness-funktionen beregnes fitness ved brug af variablerne: whiteSensorFrameCount, clockWiseRotationFrameCounter og lapTimeInFrames, fra bilens sensorsystem. Der er også inkluderet en ny boolean: "trash". Hvis trash er sand, er bilen vurderet til ikke at have kørt en rigtig omgang, men "snydt", dette checkes ud fra hvor lang tid bilen tager om at køre en omgang. Der er ganget en konstant værdi på variablerne, som forsøg på at afstemme dem efter vigtighed.

I reproduktions-funktionen, er der valgt at tage det bedste individ ud fra generationen, og så kopiere dem 1 gang. Resten af populationen er en kopi af dette indvid, med mutation.

I muterings-funktionen er der en chance for værdierne af vægtene og bias'ene bliver ændret. Her er der brugt værdier på: 0.5% chance for værdien sættes til 0, 2.5% chance for værdien ganges med -1. 2% chance for værdien blive plusset med en tilfældig værdi imellem -0.1 og 0.1. Dette er relativt svage værdier for mutation, men de er valgt, fordi vi havde problemer med at mutationerne, gjorde bilerne dårligere, da der allerede var fundet en tilfreds løsning.

Der er også blive lavet nogle konstruktors til nogle af klasserne, for at kopiere dem. Dette er nyttigt når der skal skabes en exact kopi af en bil. For ikke at få nogle problemer med reference mellem værdier skabes disse kopi-konstruktorer.

Hvis vi havde mere tid, vil vi fortsat gerne arbejde på en bedre fitness funktion, og muterings funktion. Reproduktionsfunktionen kunne også forbedres med crossover, da det vil give mere diversitet, uden nødvendigheden for at mutationerne skal gøre det, men det ser vi ikke som flaskehalsproblemet. Programmets største problem er starten. Hvis en bil kommer igennem et help "lap" ordentligt, vil udviklingen for den genetiske algoritme typisk gå meget godt. Hvis dette ikke er tilfældet, har programmet en tendens til at sidde fast. Dette kan løses på 2 måder. Enten med en bedre fitnessfunktion, som belønner en bil som når f.eks. til halvdelen af banen. Dette kunne gøres ved at tilføje en ekstra målstreg. Der kunne også ændres/laves nye variabler til at bedømme fitness-funktionen. Muteringsfunktionen, kunne også ændres til at være mere radikal, for at skabe mere diversitet i starten, men som nævnt har vi erfaret at det skaber ustabilitet i programmet, når en tilfredsstillende løsning er fundet.
