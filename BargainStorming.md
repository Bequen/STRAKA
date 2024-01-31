## Fakulty
Uživatel s oprávněním rektor bude schopen vytvořit objekt "fakulta".

Dále bude schopen fakultám přiřadit "děkana".

## Katedry
Jestliže je uživatel přiřazen jako "děkan" dané katedry, bude moct vytvořit objekt "katedra" a přiřadit mu uživatele jako "vedoucí katedry".

## Studijní obor
Jestliže je uživatel dané katedry přiřazen jako "vedoucí katedry". Bude moct vytvořit objekt jménem "studijní obor" a přiřadit k němu "garanta".

Studijní obor bude mít přiřazené kurzy v relaci buď jako "A", "B" nebo "C", společně s množstvím kreditů. Ty se mohou lišit, různé obory mohou za stejný kurz obdržet jiný počet kreditů.

Zbylé předměty, které nebudou konkrétně přiřazeny, se budou považovat jako "irrelevantní", tedy budou fungovat stejně jako předměty typu "C" a vždy budou za 1 kredit.

Dále bude možno si přihlásit maximálně 4 předměty typu "C" za semester.

Tyto nastavení budou moct měnit jak "vedoucí katedry", tak i "garant" studijního oboru.
## Kurz
Jestliže je uživatel dané katedry přiřazen jako "vedoucí katedry", bude moct vytvářet objekt "kurz".

Kurz bude mít:
- název
- zkratka
- popis
- doporučený počet kreditů (tato hodnota se sama vyplní při přiřazení kurzu studijnímu oboru, nebude se vztahovat na "irelevantní")
- doporučená literatura
- potřebné kurzy (předpoklady)
- jazyky (každý kurz může mít více)
- způsob zakončení
- možnost "irelevantní" (jestli si mohou studenti studijních oborů, které tento kurz nemají přiřazen, kurz taky vůbec zapsat)

Kurzu dále přiřadí "garanta".

Uživatel, který má vztah "garant" k nějakému kurzu, bude moct veškeré info upravovat. Zde je možnost systému schvalování:
1. má se kurz upravit rovnou?
2. nebo je třeba schválení od "vedoucího katedry"

Dále bude moct přiřadit uživatele jako "cvičící", "přednášející" nebo "vyučující".

Dále bude muset říct, kolik různých kalendářních akcí cvičení, přednáška a seminář je třeba.

### Termíny
Uživatel s oprávněním "Zkoušející" bude moct vypsat termíny zkoušky.

Uživatel s oprávněním "Zkoušející" bude moct studentovi, který je na kurzu tento semestr zapsaný, přiřadit známku a tím se studentovi označí kurz jako splněný, společně se známkou a kolikátý pokus to byl.

### Cvičící
Bude moct vytvořit _kalendářní akci_ "cvičení" k danému kurzu.
Kalendářní akce bude mít vybraný konkrétní semestr, počet studentů.

_Kalendářní akce_ bude mít přiřazeno alespoň jednu konkrétní událost.
Tato událost bude mít konkrétní čas od do.

Dále bude moct ke _kalendářní akci_ vytvářet úkoly, ty budou mít:
- čas zveřejnění
- termín odevzdání
- je možnost přetáhnout termín?
- popis
- název
- je úkol povinný?

Studenti budou moci jako objekt _řešení_ přikládat soubor s popiskem. Ten se poté označí _pro schválení_. Popř. bude moct cvičící k úkolu přidat komentář, jestliže úkol nebude správně.

Cvičící bude moct studentovi uznat zápočet.

## Student
Se bude moct zapsat na daný předmět. Bude si muset zapsat tolik kalendářních akcí každého typu, kolik bylo zvoleno garantem kurzu.

## Rozvrhář
Rozvrhář bude role přiřazena konkrétnímu uživateli ke konkrétní fakultě. Poté, co budou dokončeny všechny kalendářní akce na semestr, bude moct přiřadit každé učebnu. Bude moct vybírat konkrétní i pro konkrétní událost, ale předvyplněná bude ta na celou kalendářní akci.

Rozvrhář potřebuje vidět, které učebny jsou ještě volné. Dále potřebuje mít přehled, jestli se daná kalendářní akce do učebny vůbec vleze.

Je zde možnost nějakého automatického přiřazení, ale to by bylo na dýl.

## Semestry
Budou se vytvářet ručně a každý student, který splňuje požadavky, bude automaticky, jak přijde čas, přesunut do dalšího semestru.