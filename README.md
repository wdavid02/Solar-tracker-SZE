# `Nap követő program Arduino Uno-ra` 

## Fény érzékelés

A rendszerben 5 db LDR ellenállást használunk, ezek szolgáltatják a beeső fényről az információt. Az értékeiket analóg módon olvassa be az Arduino, majd átlagolásokkal határozzuk meg, az aktuális megvilágításnak megfelel a jelenlegi pozíció, vagy sem.
Ehhez egy tolerancia értéket határoztunk meg.


### Pozícionálás
``` r
Ezt a feladatot két szervomotor, egy horizontális és vertikális helyzetű állítja be, a vezérlő által kiadott PWM jelek alapján.
A PWM jelek létrehozásához az Arduino saját Servo.h könyvtáráshasználjuk.
```
### DC Motor - nyugalmi és aktyv helyzet

```r
Az eredeti koncepció szerint a napelemek, egy közös tengelyen, egymás mögött helyezkednek el, azonban megfelelő megvilágítás esetén a DC motor forgatja ki őket egymás mellé kiosztva, mintegy virág szirmait imitálva. Ennek a mozgásnak a szabályzásáról a CW és CCW végállás kapcsolók/gombok gondoskodnak. CW a nyugalmi helyzet érzékeléséért, míg CCW az aktív helyzet érzékeléséért felel.
```

<details>
<summary> Egyéb építőelemek</summary>

``` r
Napelem: A vezérlés nem rendelkezik róla, sorba kötött a generátorral,így feszültségük összegződik, ezek együttessen csatlakoznak a feszültség szabályozó Input lábára
```
```r
Feszültség szabályozó: Biztosítja a megfelelő feszültséget a vezérlőnek,a szervó motoroknak, valamint az LDR-eknek.
```
```r
Motor vezérlő: A DC motor meghajtásához egy motorvezétlő volt szükséges a megfelelő működés elérése érdekében
```

</details>

## Jelenleg fennálló probléma:
```r
Tinkercad szimulációs felületen az Arduino 100mV nagyságrendű PWM jelet állít elő, mely valószínűleg nem elegendő a szervók pozícionálásához
```