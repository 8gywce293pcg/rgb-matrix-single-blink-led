### @explicitHints false

## Introduksjon @unplugged
Her vil du lære å kode våre kule LED displayer. 

Få en LED til å blinke med intervallene 1 sekund på og 1 sekund av.

## Steg 1: Definer noen neopixler @fullscreen
 Trykk på ``||Neopixel||`` fra blokkmenyen.

 Klikk og dra inn blokken ``||sett strip til||`` og slipp den inn i ``||basic:ved start||`` blokken.
 
 Velg pinne ``||P0||`` og antall LED til ``||768||`` la format stå som ``||RGB (GRB)||``.

 Denne blokken brukes for å velge hvilken pinne som er koblet til LED, hvor mange LED det er og hvilken type LED. 

```blocks

let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)

```
## Steg 2: Slette minne i LED
Trykk på ``||Neopixel||`` fra blokkmenyen.

Klikk og dra inn blokken ``||strip.clear||`` plasser den under forrige blokk.

Denne blokken sletter tidligere data inni lysdidodene.

```blocks

let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()

```

## Steg 3: Velge hvilken lysdidoe som skal lyse og hvilken farge

Trykk på ``||Neopixel||`` fra blokkmenyen og klikk deretter ``||mer||``.

Klikk og dra inn blokken ``||strip set_Pixel_Color at 0 to Red||`` plasser den i ``||basic: gjenta for alltid||``. 

Denne blokken brukes for å velge hvilken LED som skal lyse (0-767) og hvilken farge.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
    strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Red))
    
})
```

## Steg 4: Send informasjon til Neopixlene
Trykk på ``||Neopixel||`` fra blokkmenyen.

Klikk og dra inn blokken ``||strip.show||`` plasser den under forrige blokk.

Denne blokken sender hvilken LED nummer og farge til LEDène som skal lyse.


```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
    strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Red))
    strip.show()
   
})
```
## Steg 5: Hvor lenge skal lysdidoen lyse
Trykk på ``||Basis||`` fra blokkmenyen.

Velg ``||basic.pause||`` og plaser denne under forrige blokk i ``||basic: gjenta for alltid||``.

Sett pausen verdien til 1000 millisekunder som er 1 sekund.

```blocks

let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
    strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(1000)
   
})
```
## Steg 6: Hvor lenge skal lysdidoen lyse
Trykk på ``||Neopixel||`` fra blokkmenyen og klikk deretter ``||mer||``.

Klikk og dra inn blokken ``||strip set_Pixel_Color at 0 to Red||`` plasser den nederst i ``||basic: gjenta for alltid||``. 

Sett fargen til Black. Det er viktig å ha samme LED nummer på begge for å kunne slå av og på LED eller å skifte farge.

```blocks

let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
    strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(1000)
    strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Black))
    
})
```
## Steg 7: Send informasjon til Neopixlene
Trykk på ``||Neopixel||`` fra blokkmenyen.

Klikk og dra inn blokken ``||strip.show||`` plasser den under forrige blokk.

Denne blokken sender hvilken LED nummer og farge til LEDène som skal skiftes.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
    strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(1000)
    strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Black))
    strip.show()
})
```
## Steg 8: Send informasjon til Neopixlene
Trykk på ``||Basis||`` fra blokkmenyen.

Velg ``||basic.pause||`` og plaser denne under forrige blokk i ``||basic: gjenta for alltid||``.

Sett pausen verdien til 1000 millisekunder som er 1 sekund.


```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
    strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(1000)
    strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Black))
    strip.show()
    basic.pause(1000)
})
```

## Steg 9: Leste ned på microbiten

hvis du har en @boardname@ tilkoblet, trykk ``|last ned|``!   Prøv nå også endre farge og hvilken LED som skal lyse for så å trykke ``|last ned|`` igjen.

Husk at LED nummer må være lik for å blinke av eller på. 

For hver endring vi gjør i koden må det lastes ned på nytt til @boardname@.
