# SuperAwesomes store plugin
Det her er SA's store plugin forked af Zodry til at virke sammen med flere versioner af skript

> [!WARNING]
>  Det er ikke sikkert dette plugin er updateret og virker.

# Eksempel

```ruby
on superawesome vote: #Tjekker om der er nogle der har voted en server
    broadcast "&3%event-player% &fvoted på serveren!" # Sender en besked til alle på serveren omkring en spiller har voted serveren
    #
    # Her kan for eksempel give spiller på din server noget
    #
    superawesome process vote id of pending vote from event-player #Fjerner spilleren fra listen af nye votes

on superawesome store purchase: #Tjekker om der er nogle der har købt noget på din server
    if "%id of event-product%" is "ID": # Udskift ID med product id'et, Det kan du finde inde på hjemmesiden
        broadcast "&f%event-offlineplayer% har købt %quantity of event-product% coins via <link:https://superawesome.dk/servers/global>&3&lBUTIK" # Broadcaster en besked med personen og hans køb, Bemærk dette er et eksempel og kan ændres
        #
        # Her kan du tilføje noget til spiller for eksempel rank eller coins
        #
        # %event-offlineplayer% = Spilleren der har købt
        # %quantity of event-product% = Mængden af det product spilleren har købt
        # %id of event-product% = Product id
        # %name of event-product% = Product navn
        # %duration of event-product% = Hvor lang tid personen har productet
        #
    else:
        superawesome store decline purchase event-id for reason "Der sketet en fejl!" #Afviser købet, Kan man bruge til vis folk har købt ranken eller andre tidspunkter

command /test [<player>] [<integer>]: #Dette er en test kommando, arg-2 = Mængden af ems. arg-1 = Spilleren der modtager dem
    permission: * 
    trigger:
        superawesome store give arg-2 emeralds to arg-1 with title "En titel" and reason "Grund" # Denne linje giver spilleren( arg-2 ) ems, og mængden på ems er( arg-1 ). Titel og grund kan ændres```
