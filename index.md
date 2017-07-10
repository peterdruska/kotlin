## Úvod do jazyka Kotlin

[Jazyk Kotlin](https://kotlinlang.org) je pomerne mladý jazyk, ktorý vznikol na základe jazyka Java, aby sa dali medzi sebou ľahko nahrádzať. Hovoríme aj, aby boli navzájom kompatibilné. V tomto jazyku je možné programovať aplikácie pre operačný systém [Android](https://www.android.com).

Je to moderný programovací jazyk, ktorý je

- Jednotný (konzistentný) – je vždy jasné, čo je zapísané
- Bezpečný – pri práci sa robí menej chýb, ako pri práci s Javou
- Medzioperačný – dá sa používať všade tam, kde Java: server, Android, …
- Dá sa programovať v rôznych nástrojoch

### Vývojové prostredie

Na základnú prácu a spoznanie sa s jazykom Kotlin budeme používať softvér, ktorý je zadarmo a volá sa [IntelliJ IDEA](https://www.jetbrains.com/idea/). Ten si treba stiahnuť a otvoriť, aby sme mohli začať.

### Vytvorenie nového projektu v IntelliJ IDEA

V IntelliJ IDEA potrebujeme po spustení urobiť pár základných úkonov, aby sme mohli napísať prvý program v jazyku Kotlin.

[![New Project](/images/NewProject.png)](images/NewProject.png)

1. Ako **Project SDK** vybrať konkrétnu verziu Javy, ktorá by v IntelliJ IDEA mala byť už doinštalovaná.
2. V časti **Additional Libraries and Frameworks** zaškrtnúť voľbu **Kotlin (Java)**
3. **Use Library** by malo obsahovať *KotlinJavaRuntime*
4. **Next**

Ďalším krokom je výber šablóny. Tento krok teraz preskakujeme, vôbec nás nezaujíma, nakoľko začneme s jazykom Kotlin *na čistom papieri*, ako sa hovorí.

[![Choose Template](images/Template.png)](images/Template.png)

Zadáme **Next**.

[![Project Name](images/Name.png)](images/Name.png)

V ďalšom kroku zadáme meno nového projektu. V ukážke to je **Hello World** a zadáme **Finish**.

### Nastavenie projektu

Teraz sa otvorí obrazovka projektu *Hello World*.

[![Project](images/Project.png)](images/Project.png)

Teraz je dôležité nastaviť jazyk Kotlin v projekte pomocou **Tools > Kotlin > Configure Kotlin in Project > All modules containing Kotlin files**. Zvyšok ponecháme tak, ako je a potvrdíme **OK**.

[![Configure Kotlin](images/ConfigureKotlin.png)](kotlin/images/ConfigureKotlin.png)

### Štruktúra projektu

Zatiaľ nás bude zaujímať zo štruktúry projektu zložka `/src/`.

[![Src](images/Src.png)](images/Src.png)

Vyznačíme ju a klikneme pravým tlačidlom. Po zobrazení ponuky vyberieme `New > Kotlin File/Class`.

[![Kotlin File](images/KotlinFile.png)](images/KotlinFile.png)

Potom zadáme meno nového súboru, napr. **HelloWorld** a potvrdíme **OK**.

[![File Name](images/FileName.png)](images/FileName.png)

IntelliJ IDEA teraz pripraví a otvorí nový súbor na úpravu.

[![Edit new file](images/EditFile.png)](images/EditFile.png)

## Prvý program

V otvorenom súbore **HelloWorld.kt** napíšeme `main` a stlačíme tabulátor.

![Main Function](screencasts/mainFunction.gif)

IntelliJ IDEA automaticky doplní hlavnú funkciu, do ktorej budeme písať akýkoľvek program v začiatkoch. Nebudeme sa teraz zaoberať, čo je funkcia, prečo sa táto volá `main`, ani čo je to tam popísané. Momentálne nám pôjde o to, čo bude v zložených zátvorkách `{}`.

![Body of the Main Function](screencasts/bodyOfMainFunction.gif)

Aby sme ten prvý program skúsili, do spomínaných zložených zátvoriek napíšeme tento príkaz:

```kotlin
println("Toto je môj prvý program v jazyku Kotlin!")
```

Funkcia `main` bude vyzerať nasledovne:

```kotlin
fun main(args: Array<String>) {
    println("Toto je môj prvý program v jazyku Kotlin!")
}
```

Pre spustenie programu pravým tlačidlom klikneme do programu, ktorý sme práve napísali a vyberiem **Run HelloWorldKt**.

![Run program](screencasts/runProgram.gif)

Výsledok vidíme v dolnej časti, v tzv. konzole.

[![Console](images/Console.png)](images/Console.png)

Kde sa vypísal text *Toto je môj prvý program v jazyku Kotlin!*

[![Console](images/Console2.png)](images/Console2.png)

O funkcii `println()` si povieme viac neskôr.

## Základné dátové typy

Pri programovaní budeme vždy pracovať s typmi údajov. V bežnom živote sa môžeme stretnúť s číslami, s textami a podobne. V jazyku Kotlin to je podobné a zo začiatku budeme rozlišovať tri jednoduché dátové typy: **textové reťazce** (`String`), **celé** čísla (`Int`), **reálne čísla** (`Double`).

### Int

Celé čísla sú jednoduché na rýchle pochopenie. Píšu sa bez desatinnej bodky. Skúsme do funkcie `main` napísať tento zdrojový kód:

```kotlin
println(3 + 4)
```

Funkcia `main` bude teda vyzerať takto:

```kotlin
fun main(args: Array<String>) { 
    println(3 + 4)
}
```

Keď program spustíme, výsledok bude vypísaný do konzoly, výsledok bude **7**. Rovnakým spôsobom sa dajú robiť akékoľvek základné matematické operácie.

### Double

Reálne čísla sa zapisujú s desatinnou bodkou. Skúsme napr.:

```kotlin
fun main(args: Array<String>) { 
    println(2.9 + 4.1)
}
```

Výsledok bude **7.0**.

Rozdiel medzi celým a reálnym číslom v programovacom jazyku Kotlin je dosť podstatný. Náš mozog tie čísla berie za rovnaké, pre počítače sú však odlišné a inak k nim musíme pristupovať. Napr. pri celočíselnom delení so zvyškom musíme byť v tomto veľmi opatrní.

### String

Ďalším jednoduchým typom sú reťazce. S nimi sme sa stretli pri prvej ukážke. Každý reťazec sa totiž zapisuje do úvodzoviek. Keď ho chceme vypísať do konzoly, použijeme takýto zápis:

```kotlin
println("Toto je super reťazec 3000!")
```

Všetko, čo je uzavreté do úvodzoviek sa chápe ako reťazec, čiže usporiadná množina znakov. Uvedené číslo 3000 je v tomto príklade pre jazyk Kotlin tiež reťazec, nie číslo.

Spustenie tohto programu vypíše text „**Toto je super reťazec 3000!**“.

## Konštanty

Keď chceme uchovávať nejakú hodnotu, napr. číslo 3,14 a používať ju v programe na viacerých miestach bez toho, aby sme si túto hodnotu museli pamätať alebo neustále zapisovať, použijeme konštantu. Definuje sa takto:

```kotlin
val pi = 3.1415
```

Definícia začína vyhradeným slovom `val`, za ktorým ide vlastné meno, ktoré určujeme my. Potom spravidla nasleduje znamienko rovná sa `=` a za ním hodnota, ktorú táto konštanta nadobúda.

Keď chceme vypočítať obvod kruhu, použitie konštánt bude nasledovné:

```kotlin
fun main(args: Array<String>) {
    val pi = 3.1415
    val r = 4.0
    val perimeter = 2 * pi * r
    println("Obvod kruhu s polomerom $r je $perimeter.")
}
```

### Definovanie typu

Definovanie konštanty vieme uskutočniť aj riadnym určeným typu. Napríklad pre vyššie definovanú konštantú **pí** to bude takto:

```kotlin
val pi: Double = 3.1415
```

Za meno konštanty zadáme dvojbodku a za ňou meno typu, v tomto prípade `Double`.

Rovnako sa určuje aj typ `Int` alebo `String`. Napríklad:

```kotlin
val retazec: String = "Toto je konštanta typu String"
val celeCislo: Int = 42
```

Konštanty sa preto volajú konštanty, lebo sú **konštantné** a nemôžu sa meniť. Čiže ak už máme konštantu `celeCislo` rovnú hodnote 42, neskôr v programe nemôžeme urobiť nové priradenie:

```kotlin
celeCislo = 43
```

Program potom zahlási chybu a nespustí sa. Napríklad takýto:

```kotlin
fun main(args: Array<String>) {
    val celeCislo: Int = 42 // prvé priradenie do konštanty
    celeCislo = 43 // toto sa nemôže už, konštanta sa nedá zmeniť po jej zadefinovaní
}
```

## Premenné

Aby sme im mohli hodnoty meniť, k dispozícii máme premenné, ktoré sa volajú premennými preto, že sa dajú **premeniť**. Teda ich hodnoty sa dajú premeniť.

Ich definícia začína vyhradeným slovom `var`:

```kotlin
var vekCloveka: Int = 18
```

Neskôr sa vek človeka môže prirodzene zmeniť kedykoľvek v programe:

```kotlin
fun main(args: Array<String>) {
    var vekCloveka: Int = 18 // prvé priradenie
    vekCloveka = 19 // druhé priradenie, premenná sa takto môže
}
```

A program žiadnu chybu nezahlási.

## Reťazce

Veľakrát budeme potrebovať pracovať s reťazcami. Napríklad potrebujeme vypísať oznam cestujúcim na autobusovej stanici, že autobus do Martina bude meškať 15 minút:

```kotlin
fun main(args: Array<String>) {
    val text: String = "Autobus do Martina bude meškať 15 minút."
    println(text)
}
```

Najprv definujeme konštantu `text` typu `String`, do ktorej vložíme reťazec s informáciou o meškaní. Na ďalšom riadku hodnotu tejto konštanty vypíšeme `println(text)`.

### Reťazce + konštanta/premenná

Čo ale v prípade, že autobus bude meškať 14 minút? A čo 13? A čo keď 23? Nedáva zmysel túto hodnotu neustále prepisovať v reťazci, keď ju môžeme odtiaľ vyňať a meniť ju na prehľadnejšom mieste tak, že z nej urobíme novú konštantu:

```kotlin
val delay: Int = 15
```

Následne textovú konštantu upravíme tak, aby sme hodnotu konštanty `delay` v ňom mali:

```kotlin
val text: String = "Autobus do Martina bude meškať $delay minút."
```

Čiže celý program bude takýto:

```kotlin
fun main(args: Array<String>) {
    val delay: Int = 15
    val text: String = "Autobus do Martina bude meškať $delay minút."
    println(text)
}
```

Teraz máme jedno pevné miesto, kde meškanie vždy upravíme podľa potreby a táto nová hodnota sa potom premietne do výsledného reťazca zavolaním mena konštanty/premennej pomocou symbolu dolár `$delay`.

### Spájanie reťazcov

Čo v prípade, že máme dva reťazce:

```kotlin
val words1: String = "Ahoj Svet."
val words2: String = "Učím sa programovať."
```

A chceme ich spojiť dohromady. Je to veľmi jednoduché:

```kotlin
val allWords: String = words1 + words2
```

Celý program:

```kotlin
fun main(args: Array<String>) {
    val words1: String = "Ahoj Svet."
    val words2: String = "Učím sa programovať."
    val allWords: String = words1 + words2
    println(allWords)
}
```

Vety by mali byť oddelené medzerou, preto pridajme medzeru medzi reťazce:

```kotlin
fun main(args: Array<String>) {
    val words1: String = "Ahoj Svet."
    val words2: String = "Učím sa programovať."
    val allWords: String = words1 + " " + words2
    println(allWords)
}
```

## Boolean - Rozhodovací typ

Jeden typ v programovaní sa tak trochu vymyká bežnému ľudskému chápaniu, ale len chvíľu. Potom si na človeka zasadne ako ovad a zvykne už nepustiť. Je to tzv. **rozhodovací typ**, v jazyku Kotlin sa označuje názvom `Boolean`. Premenná tohto typu vyzerá takto:

```kotlin
var delayed: Boolean = false
```

Okrem hodnoty `false` môže tento typ nadobúdať už len hodnotu `true`. Môžeme si ho predstaviť ako vypínač svetla: **svieti**, **nesvieti**.

### Logika vecí

Typ `Booblean` sa používa pri logickom uvažovaní, rozhodovaní. Napríklad skúsme tento program:

```kotlin
fun main(args: Array<String>) {
    println(3 < 4)
}
```

Hodnota `true` vo výpise je typu `Boolean`. Rovnakým spôsobom môžeme zadať rôzne porovnávacie operácie:

```kotlin
>  // väčší
<  // menší
>= // väčší rovný
<= // menší rovný
!= // rôzny
== // rovný
```

Ich výsledkom bude práve typ `Boolean`, a síce hodnota `true` alebo `false`. Skúsme niečo takéto:

```kotlin
fun main(args: Array<String>) {
    val solution: Boolean = 42 >= 15
    println(solution)
}
```

Výsledok znovu vypíše ako `true`. Vyššie uvedený zápis vyzerá zvláštne, no robí len toľko, že výsledok porovnania `42 >= 15` vloží do konštanty `solution`.

### Logika viac vecí

Stáva sa, že treba rozhodnúť viac vecí naraz. Napríklad zistiť, či platí trojuholníková nerovnosť, či je teplota vzduchu a vody vhodná na kúpanie, či prídu všetci atď. Na zisťovanie hodnoty `true` alebo `false` viac vecí naraz používame operátory:

- `||` – alebo
- `&&` – a zároveň
- `!` – negácia

Porovnajme viac čísel voči nule naraz:

```kotlin
fun main(args: Array<String>) {
    val a: Int = 1
    val b: Int = 4

    val aAndB = a > 0 && b > 0 // Zistenie (a > 0 a zároveň b > 0)

    println("($a > 0 && $b > 0) = $aAndB") // výpis zloženého porovnania
}
```

Operátor alebo:

```kotlin
fun main(args: Array<String>) {
    val a: Int = 1
    val b: Int = -1

    val aOrB = a > 0 || b > 0 // Zistenie (a > 0 alebo b > 0)

    println("($a > 0 || $b > 0) = $aOrB") // výpis zloženého porovnania
}
```

Operátor negácia:

```kotlin
fun main(args: Array<String>) {
    val a: Int = 1

    val aNot = !(a > 0) // Zistenie negácie výrazu (a > 0)

    println("!(a > 0) = $aNot") // výpis zloženého porovnania
}
```

Typ `Booblean` je oničom, pokiaľ sa bližšie nepozrieme na podmienky.

## Podmienky `if`

Autobus raz mešká, inokedy nie. Cestujúcim nemôžeme vypísať informáciu *„autobus mešká 0 minút“*. Bolo by to trochu … *blbé*. Namiesto toho musíme zistiť, o aké meškanie sa jedná a rozlíšiť dva rôzne prípady.

Vytvorme program, v ktorom bude v jednej konštante doba meškania:

```kotlin
fun main(args: Array<String>) {
    val delay: Int = 15
}
```

Ak autobus bude meškať, vypíšeme cestujúcim túto informáciu na tabuli. Na tieto a podobné prípady máme v programovaní podmienky. V jazku Kotlin sa zapisujú pomocou vyhradeného slova `if`:

```kotlin
if (PODMIENKA) {
    // pokiaľ je podmienka splnená (true), vykonajú sa príkazy tu
}
```

Miesto troch bodiek v príkaze budú konkrétne veci (ďalšie príkazy). V prípade autobusu:

```kotlin
if (delay > 0) {
    println("Autobus mešká $delay minút. Ospravedlňujeme sa!")
}
```

Čiže ak meškanie bude väčšie ako nula, vypíšeme o tom informáciu. Celý program:

```kotlin
fun main(args: Array<String>) {
    val delay: Int = 15

    if (delay > 0) {
        println("Autobus mešká $delay minút. Ospravedlňujeme sa!")
    }
}
```

Po spustení programu dostaneme na výpise **„Autobus mešká 15 minút. Ospravedlňujeme sa!“** Čo v prípade, že do konštanty `delay` zadáme nulu? Program nič nevypíše, lebo podmienka `delay > 0` nie je splnená (nadobúda hodnotu `false`).

V takom prípade, keď chceme dať cestujúcim informáciu, že autobus ide načas, musíme použiť druhú vetvu príkazu `if`, ktorá sa volá vyhradeným slovom `else` takto:

```kotlin
if (PODMIENKA) {
   // príkazy vo vetve if, pokiaľ je PODMIENKA splnená (true)
} else {
   // príkazy vo vetve else, pokiaľ je PODMIENKA nesplnená (false)
}
```

Program s autobusom bude takýto:

```kotlin
fun main(args: Array<String>) {
    val delay: Int = 15

    if (delay > 0) {
        println("Autobus mešká $delay minút. Ospravedlňujeme sa!")
    } else {
        println("Autobus ide načas. Stihnete všetko, čo plánujete!")
    }
}
```

Teraz keď zadáme do konštanty `delay` hodnotu nula, vypíše sa reťazec z vetvy `else`.

### Reťazce v podmienkach

Do podmienok `if` sa dajú vkladať aj porovnávačky reťazcov. Napríklad, či obsahuje nejaký znak, akú má dĺžku alebo či sú reťazce rovnaké. Podmienok sa dá vymyslieť mnoho, tu sú základné z nich.

#### Či reťazec obsahuje nejaký znak

```kotlin
fun main(args: Array<String>) {
    val sentence: String = "Odpoveď na otázku života, vesmíru a vôbec."

    if (sentence.contains('e')) {
        println("Reťazec obsahuje znak 'e'")
    }
}
```

Konštanta `sentence` je typu `String`, preto nad ňou môžeme zavolať funkciu (o funkciách neskôr) `contains()`, do ktorej vložíme symbol znaku, ktorý hľadáme.

#### Či má reťazec požadovanú dĺžku

```kotlin
fun main(args: Array<String>) {
    val password: String = "nbusr123"

    if (password.length <= 3) {
        println("Heslo je príliš krátke.")
    } else {
        println("Heslo je akurátne.")
    }
}
```

#### Či sú reťazce rovnaké

```kotlin
fun main(args: Array<String>) {
    val username: String = "jankohrasko"
    val username2: String = "janhrach"

    if (username == username2) {
        println("Používateľské meno už existuje, vymysli si prosím, iné.")
    } else {
        println("Tvoje používateľské meno je voľné.")
    }
}
```

#### Či je reťazec prázdny

```kotlin
fun main(args: Array<String>) {
    val username: String = "jankohrasko"

    if (username.isEmpty()) {
        println("Zadaj prosím nejaké používateľské meno.")
    } else {
        println("Výborne, odteraz sa budeš volať $username.")
    }
}
```

![isEmpty](screencasts/isEmpty.gif)

#### Zanorené podmienky

Podmienky sa dajú do seba (v prípade fakt nutnej potreby) aj zanárať:

```kotlin
if (PODMIENKA) {
    if (PODMIENKA2) {
        if (PODMIENKA3) {
            if (PODMIENKA4) {
                if (PODMIENKA5) {
                }
            }
        } else {
            if (PODMIENKA6) {
                // Ale bacha na to, lebo sa môžeš stratiť tak, ako sa len podmienka v podmienke môže stratiť!
            }
    } else {
        // Tu už končia všetky srandy.
    }
}
```

## Podmienky `when`

Okrem podmienok `if` máme v jazyku Kotlin ešte aj podmienky `when`. Tento príkaz môžeme chápať ako prepínač, alebo rozhodovač stavov. Majme číslo, o ktorom chceme rozhodnúť, do ktorého intervalu patrí:

```kotlin
val x: Int = 42

when (x) {
    in 1..10 -> print("Číslo $x patrí do intervalu [1, 10]")
    in 11..20 -> print("Číslo $x patrí do intervalu [11, 20]")
    in 21..30 -> print("Číslo $x patrí do intervalu [21, 30]")
    in 31..40 -> print("Číslo $x patrí do intervalu [31, 40]")
    in 41..50 -> print("Číslo $x patrí do intervalu [41, 50]")
    else -> print("Číslo $x nepatrí do žiadneho z uvedených intervalov.")
}
```

Vetva `else` je na to, aby sme zachytili aj možnosť, ktorá ja iná, ako všetky vymenované v prepínači. Prípadne ak chceme iba zistiť, o aké číslo sa jedná a vypísať jeho slovné pomenovanie:

```kotlin
val number: Int = 2

when (number) {
    1 -> print("Jeden")
    2 -> print("Dva")
    3 -> print("Tri")
    else -> print("Číslo neviem pomenovať.")
}
```

Dá sa aplikovať aj na reťazce:

```kotlin
val name: String = "Peter"

when (name) {
    "Peter" -> println("$name, urob niečo!")
    "Veronika" -> println("$name, oddýchni si!")
    else -> println("$name, teba nepoznám!")
}
```

## Zoznamy

Zoznamy sú super a neskôr zistíš, prečo.

Majme **zoznam** čísel, ktoré sa definuje volaním funkcie `listOf()`:

```kotlin
val fib = listOf(1, 1, 2, 3, 5, 8, 13, 21)
```

(Kto zistí, o akú postupnosť čísel sa jedná a aké by boli ďalšie čísla?)

Keď chceme vypísať konkrétny prvok tohto zoznamu, jednoducho to spravíme volaním mena zoznamu `fib` s uvedením indexu prvku do hranatých zázvoriek takto:

```kotlin
println(fib[0]) // Vypíše prvé číslo 1
```

**Číslovanie indexov začína pri zoznamoch od nuly.** Na to pamätaj, budeš to potrebovať! Vypísanie posledného prvku v terajšom zozname sa dá urobiť takto:

```kotlin
println(fib[7]) // Vypíše posledné číslo 21
```

Ale lepšie to je urobiť takto:

```kotlin
println(fib.last()) // Vypíše posledný prvok bez ohľadu na veľkosť zoznamu
```

Takto sa dá vypísať prvý prvok:

```kotlin
println(fib.first()) // Vypíše prvý prvok
```

Vymeniť hodnotu na konkrétnom mieste je jednoduché a robí sa takto:

```kotlin
fib[0] = 4 // Miesto pôvodnej 1 na nultom mieste bude teraz číslo 4
```

Dá sa rozhodnúť, či je zoznam prázdny volaním funkcie `isEmpty()` nad daným zoznamom:

```kotlin
if (fib.isEmpty()) {
    println("Zoznam je prázdny")
}
```

Prípadne zistiť, či sa v zozname nachádza konkrétny prvok:

```kotlin
if (fib.contains(5)) {
    println("Zoznam obsahuje číslo 5")
}
```

Zoznamy nemusia byť len celočíselné, ako je to v prípade zoznamu `fib`, ale aj plné reťazcov:

```kotlin
val names = listOf("Veronika", "Matej", "Jakub")
```

Môžu byť aj zmiešané:

```kotlin
val allOrNothing = listOf("Peter", 42, -3.14)
```

Zoznam `allOrNothing` obsahuje jeden reťazec, jedno celé číslo a jedno reálne číslo. S ním sa pracuje tiež rovnako, ako s akýmkoľvek iným zoznamom.

S takým zoznamom sa dá robiť presne to isté, čo s číselným zoznamom. Zisťovať, či obsahuje nejaký prvok, či je prázdny alebo získať konkrétny prvok zoznamu.

### Zmena zoznamu

Povedzme, že chceme zoznam `fib` doplniť o ďalšie prvky. Urobiť to nemôžeme, lebo vo svojom základe je zoznam nemenný, definovaný funkciou `listOf()`. Keď ho chceme dopĺňať, alebo prvky odstraňovať, musíme ho definovať ako meniteľný takto:

```kotlin
val fib = mutableListOf(1, 1, 2, 3, 5, 8, 13, 21)
```

Teraz dokážeme do zoznamu **pridať nové prvky** pomocou funkcie `add()`:

```kotlin
fib.add(55)
```

Takéto volanie jednoducho pridá do zoznamu `fib` na jeho koniec nový prvok `55`. Keď chceme vložiť konkrétny prvok na konkrétne miesto, nie na koniec, musíme určiť index, na ktorý tento prvok vkladáme:

```kotlin
fib.add(8, 34)
```

V tomto prípade na index číslo `8` vkladáme do zoznamu číslo `34`. Je dobré si priebežný stav zoznamu kontrolovať jednoduchým výpisom:

```kotlin
println(fib)
```

Zo zoznamu vieme **prvky aj odstraňovať** pomocou funkcie `removeAt()`:

```kotlin
fib.removeAt(3)
```

Táto funkcia odstráni zo zoznamu prvok na konkrétnom indexe. Prípadne sa dá použiť funkcia `remove()`:

```kotlin
fib.remove(13)
```

Treba spomenúť, že tu sa **odstraňuje konkrétny prvok zo zoznamu.** Ešte lepšie to ale vidno na zozname mien `names`, ktorý musíme najskôr definovať ako meniteľný:

```kotlin
val names = mutableListOf("Veronika", "Matej", "Jakub")
names.add("Barbora") //  Pridáme nový prvok
println(names)

names.remove("Matej") // Odstránime konkrétny prvok
println(names)

names.removeAt(0) // Odstránime prvok na indexe 0
println(names)
```

## Cykly

Cyklus, to je niečo, čo sa neustále opakuje. Napríklad východ Slnka sa opakuje každý deň. Rovnako aj jeho západ.

[![Sunrise Sunset Cycle](images/sunrise_sunset.gif)](images/sunrise_sunset.gif)

Každý deň si umývaš zuby, obliekaš sa. Každý deň ráno vstaneš, naješ sa približne v ten istý čas alebo, keď si hladný/hladná. Celý náš život je prežívaný v cykloch.

Rovnako sú cykly dôležité aj v programovaní. V jazyku Kotlin rozlišujeme dva druhy cyklov:

- `for` cyklus s pevným počtom opakovaní. To je také, keď povieme, že niečo sa zopakuje 365 krát.
- `while` cyklus s opakovaním, kým je splnená podmienka. To je také, ako keď ti mama povie: *„Keď si upraceš izbu, pôjdeš von!“* Kľúčová je tá podmienka *„keď si upraceš izbu“.* Keď je podmienka splnená, cyklus škriepok končí.

### `For` cyklus

Keď chceme niečo zopakovať toľkokrát, koľko určíme. Často sa používa na prechádzanie zoznamov:

```kotlin
val names = mutableListOf("Veronika", "Matej", "Jakub")

for (name in names) {
    println(name)
}
```

Vymenovanie prvkov zoznamu `names` sa robí tak, že do zátvoriek za slovo `for` sa uvedie názov konštanty (`name`), do ktorej sa pri každom opakovaní vloží vždy nasledujúca hodnota zoznamu `names` takto: `(name in names)`. Slovo `in` znamená samozrejme *„v“*. Čiže tento cyklus sa dá prečítať takto **„pre každé meno v menách opakuj“**.

V cykle vieme prechádzať akýkoľvek zoznam:

```kotlin
val allOrNothing = listOf("Peter", 42, -3.14)

for (element in allOrNothing) {
    println(element)
}
```

V každom opakovaní (iterácii) sa do konštanty `element` dostanú postupne prvky poľa `allOrNothing`.

V cykle sa dá prejsť každý znak reťazca:

```kotlin
val name: String = "Janko Hraško"

for (char in name) {
    println(char)
}
```

Preto je to možné, lebo reťazce sú tiež kolekcie. Konkrétne kolekcie znakov.

Zaujímavé je cykly spájať s podmienkami. Napríklad ak chceme spočítať, koľko znakov **o** sa nachádza v reťazci:

```kotlin
val name: String = "Janko Hraško"
var count: Int = 0

for (char in name) {
    if (char == 'o') {
        count = count + 1
    }
}
println("Písmeno „o“ sa v reťazci „$name“ nachádza $count krát.")
```

### `While` cyklus

Kým je splnená riadiaca podmienka, cyklus bude bežať. Takže bacha na zacyklenie, na tzv. nekonečný cyklus (ang. infinite loop). Napríklad skúsme to najprv veľmi jednoducho, že keď číslo dosiahne hodnotu 100000 (stotisíc), tak cyklus skončí. V jeho tele postupne tieto čísla vypíšme. Vypisovať ich ručne by dalo jednému asi trochu zabrať:

```kotlin
var number: Int = 0
while (number <= 100000) {
    println(number)
    number = number + 1 // treba ho zväčšovať o jedna, inak by to bol nekonečný cyklus
}
```

Premennú `number` musíme nechať zväčšiť o `1`, pretože sa touto hodnotou chceme dostať až na 100000. Bez zväčšovania by to nenastalo a cyklus by donekonečna vypisoval hodnotu nula. Nikdy by sa nezastavil.

Dobre, aby sme si naliali čistej Kofoly, vypísať stotisíc čísel nie je až taká práca. Čo v prípade, keď všetky tie čísla chceme spočítať?

```kotlin
1 + 2 + 3 + 4 + 5 + … + 99999 + 100000 = ?
```

V matematike by sme na to rozžhavili [vzorec na výpočet súčtu aritmetickej postupnosti](https://sk.wikipedia.org/wiki/Aritmetická_postupnosť). Programovanie má v tomto obrovskú výhodu, že výpočty si vďaka tomu môžeme zjednodušiť. Samozrejme, matematike sa v programovaní nevyhneme, skôr naopak, je tu prítomná neustále. Súčet aritmetickej postupnosti do 100000 vieme urobiť takto:

```kotlin
var number: Int = 0
var sum: Int = 0

while (number <= 100000) {
    sum = sum + number // postupne k pôvodnej sume pridávame nové číslo a vložíme naspäť do sumy
    number = number + 1 // vstupuje do podmienky, preto postupne navyšujeme
}
println("1 + 2 + … + 99999 + 100000 = $sum")
```

## Funkcie

Predstavte si situáciu, keď pri programovaní musíte napísať tisíckrát to isté. Jeden by sa z toho aj zbláznil. Programovanie má to čaro, že si vďaka nemu viete veci zjednodušovať. Na ušetrenie času pri písaní toho istého má programovanie **funkcie**.

Sú to malé kúsky kódu, ktoré niečo robia. Niečo, čo v celom programe použijeme minimálne raz. Sú logicky uzavreté, čo znamená, že jedna funkcia napríklad zisťuje maximum z dvoch čísel, druhá funkcia bude určovať, či je číslo kladné, záporné alebo nula, ďalšia zašifruje reťazec, atď.

Ukážme si, ako na to v jazyku Kotlin.

Funkcia sa definuje takto:

```kotlin
fun helloWorld() {
    // Tu pôjdu príkazy funkcie
}
```

Toto je najzákladnejší spôsob definovania funkcie. Popíšme si ju. Najprv ide vyhradené slovo `fun`, za ktorým nasleduje meno funkcie `helloWorld`. To môžeme napísať, aké chceme, ale s malým začiatočným písmenom a ideálne čo najviac popisné, že čo funkcia robí. Potom nasledujú okrúhle zátvorky `()`, do ktorých zatiaľ nič nedávame. Nasledujú zložené zátvorky `{}`, do ktorých napíšeme nejaké príkazy podľa toho, čo od funkcie chceme, aby robila. Tak urobme funkciu, ktorá vypíše *Hello World!*

```kotlin
fun helloWorld() {
    println("Hello World!")
}
```

**BACHA!** Aby sme však predišli chybám, funkcie sa nedefinujú do žiadnej inej funkcie. Čiže **akúkoľvek funkciu napíšeme mimo funkciu `main`**.

Keď chceme funkciu `helloWorld()` zavolať, aby vypísala požadovaný text, musíme tak učiniť v inej funkcii. Pre zjednodušenie ju zavoláme vo funkcii `main` tak, že napíšeme jej meno a prázdne okrúhle zátvorky:

```kotlin
fun main(args: Array<String>) {
    helloWorld()
}
```

Spustením programu sa teraz skutočne vypíše *Hello World!* Toto je však veľmi jednoduché použitie funkcie na to, aké magické čáry–máry to dokáže.

Skúsme teraz do zadaného textu, napr.:

```kotlin
Programovanie je super!
```

Vložiť medzery po každom znaku tak, že výsledok bude takýto:

```kotlin
P r o g r a m o v a n i e   j e   s u p e r !
```

Do funkcie, ktorú si vytvoríme, budeme môcť zadať ľubovoľný text pri jej zavolaní. Preto bude vyzerať takto:

```kotlin
fun printWithSpaces(text: String) {
    for (char in text) {
        print(char + " ") // Vypíše znak po znaku, za ktorým nasleduje medzera
    }
    println() // Vypíše prázdny riadok
}
```

Zapís `printWithSpaces(text: String)` hovorí o tom, že do funkcie bude **vstupovať** reťazec (typ `String`), ktorý sa vloží do konštanty menom `text`. Čiže keď zavoláme túto konštantu vo vnútri funkcie `printWithSpaces()`, máme v nej uložený reťazec, ktorý sme vložili do funkcie pri jej volaní. Napríklad takto:

```kotlin
fun main(args: Array<String>) {
    printWithSpaces("Programovanie je super!")
}
```

Keď sa takto funkcia zavolá, začne sa jej vnútro vykonávať. Vstupuje do nej reťažec `Programovanie je super!`, ktorý sa začne spracovávať `for` cyklom znak po znaku. Každý znak vypíšeme volaním funkcie `print()` s tým, že za ten znak pridáme medzeru: `char + " "`.

## Objekty a triedy
