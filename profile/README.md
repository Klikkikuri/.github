# Klikkikuri – uutiset ilman klikkiotsikoita

![](assets/logo.png)

**Klikkikuri** on selainlaajennus, joka tunnistaa ja oikaisee sensaatiohakuiset uutisotsikot kun selailet verkkolehtien uutissivuja. Tarjoamme ainoana suomalaisena ratkaisuna luotettavampaa uutisointia suomalaisille uutisten kuluttajille hyödyntäen tekoälyä ja avoimen lähdekoodin teknologiaa.

Koe uutiset luotettavimmiksi.

## Ominaisuudet

 - **Automaattinen otsikoiden oikaisu**: muokkaa klikkiotsikot vastaamaan paremmin uutisen sisältöä.
 - **Helppokäyttöisyys**: toimii useimmissa verkkoselaimissa ilman monimutkaisia asennusta.
 - **Avoin lähdekoodi**: varmistaa läpinäkyvyyden ja jatkuvan kehityksen.
 - **Freemium-malli**: ilmainen perusversio, maksullinen korjaus paywall-sivustoille.

## Toiminta

### Palvelun toimintamalli

![](assets/modus-operandi-2024-09-29-0135.png)

Näin Klikkikuri tarkistaa uutisen sisällön ja otsikon vastaavuuden:

1. Palvelu noutaa uuden uutisen uutissivustolta​.
2. Artikkelista tunnistetaan uutiseen liittyvät sidosryhmät ja eri intressitahot​.
3. Tietämystietokannasta etsitään tietoa intressitahojen yhteyksistä uutiseen​.
4. Uutisartikkelia täydennetään tietämystietokannan tiedoilla intressitahoista​ –  tällä pyritään takaamaan uutisen parempi taustoitus ja vähentämään kielimalleille tyypillistä hallusinaatiota.
5. Kielimalli arvioi alkuperäisen otsikon sopivuutta ja ehdottaa tarvittaessa uutta otsikkoa.
6. Jos uusi otsikko on luotu, se tallennetaan otsikkotietokantaan kielimallin tarjoamien perustelujen kanssa.​
7. Tietokannasta luodaan päivitetty vedos otsikoista ja niiden tunnisteista.​ Selainlaajennus lataa tämän listan ajoittain automaattisesti.
8. Käyttäjä avaa ja lataa uutissivun normaalisti. Asennettu Klikkikurin selainlaajennus tunnistaa sivun tuetuksi uutissivustoksi, lukee ladatun otsikkolistan ja vaihtaa uutissivuston otsikot listan tunnisteiden pohjalta.​
9. Näin käyttäjä näkee uutissivuston korjatuilla otsikoilla ilman tarvetta manuaaliselle intervaatiolle.​

### Yksityisyys

Klikkikuri-laajennus ei kerää käyttäjältä tietoja muissa tilanteissa kuin:
- Käyttäjä erikseen laittaa päälle vikatilanteiden raportointityökalun
- Käyttäjä osallistuu käyttäjätutkimukseen, jolloin kerättävä tieto on erikseen määritelty ja rajattu
- Käyttäjä ilmoittaa virheellisestä otsikosta

Käyttämällä paikallista vedosta tietokannasta palveluun ei tarvitse myöskään lähettää kutsuja, jolloin palvelu ei voi seurata käyttäjien uutissivusto-käyttäytymistä.

## Kiitokset

Klikkikurin kehitys on mahdollista kiitos [Jyväskylän Yliopiston](https://www.jyu.fi), [Jyväskylän kaupungin](https://www.jyvaskyla.fi) sekä [Jyväskylän Ammattikorkeakoulun](https://www.jamk.fi) omistaman [Jyväskylän Yritystehtaan myöntämän rahoituksen](https://yritystehdas.fi/tuotekehitysrahoitus) ansiosta. Tehty ❤️ Jyväskylässä.
