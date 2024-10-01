# Klikkikuri - Uutisia ilman klikkiotsikoita

![](assets/logo.png)

**Klikkikuri** on selainlaajennus, joka tunnistaa ja korjaa sensaatiohakuiset uutisotsikot. Se tarjoaa luotettavampaa uutisointia suomalaisille uutisten kuluttajille hyödyntäen tekoälyä ja avoimen lähdekoodin teknologiaa.

## Ominaisuudet

 - **Automaattinen otsikoiden korjaus**: Muokkaa klikkiotsikot vastaamaan paremmin uutisen sisältöä.
 - **Helppokäyttöisyys**: Toimii useimmissa verkkoselaimissa ilman monimutkaisia asennusta.
 - **Avoin lähdekoodi**: Varmistaa läpinäkyvyyden ja jatkuvan kehityksen.
 - **Freemium-malli**: Ilmainen perusversio, maksullinen korjaus paywall-sivustoille.

## Toiminta

### Palvelun toimintamalli

![](assets/modus-operandi-2024-09-29-0135.png)

1. Palvelu noutaa uuden uutisen uutissivustolta​
2. Artikkelista tunnistetaan uutiseen liittyvät sidosryhmät ja eri intressitahot​
3. Tietämystietokannasta etsitään tietoa intressitahojen yhteyksistä uutiseen​
4. Uutisartikkelia täydennetään tietämystietokannan tiedoilla intressitahoista​
5. Kielimalli arvioi alkuperäisen otsikon sopivuutta, ja ehdottaa tarvittaessa uutta otsikkoa.
6. Jos uusi otsikko on luotu, se tallennetaan otsikkotietokantaan kielimallin tarjoamien perustelujen kanssa.​
7. Tietokannasta luodaan päivitetty lista otsikoista ja niiden tunnisteista.​
8. Käyttäjä lataa uutissivun normaalisti. Asennettu selainlaajennus tunnistaa sivun tuetuksi uutissivustoksi, lataa palvelusta otsikkolistan, ja vaihtaa uutissivuston otsikot listan tunnisteiden pohjalta.​
9. Käyttäjä näkee uutissivuston korjatuilla otsikoilla ilman tarvetta manuaaliselle intervaatiolle.​
