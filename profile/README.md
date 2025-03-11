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

## Usein kysyttyjä kysymyksiä

### Kuinka luotettava Klikkikuri on?

Varmistaakseen luotettavuutta klikkikurin oma koodi on avointa lähdekoodia, jonka toiminnan luotettavuuden voi ulkoinen taho arvioida ja varmistaa. Semi-selkokieliset käskyt joita kielimallille annetaan ovat luettavissa [`meri/src/prompts`](https://github.com/Klikkikuri/meri/tree/main/src/meri/prompts) -kansiossa, joista oleellisin on [`article_title_inst.md.j2`](https://github.com/Klikkikuri/meri/blob/main/src/meri/prompts/artcile_title_inst.md.j2).

Kielimallien tyypillistä hallusinaatiota vastaan uutisen tietoa laajennetaan toistaiseksi parhaaksi tiedetyllä keinolla, jossa uutisen lisäksi kielimallille kerrotaan ajantasaisia ydinseikkoja taustoittavista tekijöistä.

Kielimalleihin rakennettuja sensuuri-, puolueellisuus-, ja ennakkoasenneteita vastaan välttämiseksi klikkikuri pyrkii käyttämään vähintään kolmea eri kielimallia eri kulttuureista. Esimerkkejä tälläisistä tilanteista ovat Amerikkalaisen ChatGPT:n haluttomuus käsitellä laittomuuksia[^chatgpt-policy] tai seksuaalisuuteen liittyviä aiheita[^chatgpt-no-nsfw], Kiinalaisen Deepseekin haluttomuus sanoa mitään kriittistä Kiinan toimista[^deepseek-tian][^deepseek-cn-prop], tai Elon Muskin omistaman Grokiin sisäänrakennettu käsky olla "Anti-woke"[^xai-antiwoke][^xai-rebel].

### Näenkö alkuperäisen otsikon mistään?

Klikkikuri muuttaa ainoastaan otsikot linkeissä, kuten etusivulla jossa tyypillisesti on ainoastaan otsikko sekä mahdollisesti ingressi. Varsinaisen artikkelin otsikko jätetään vastamaan alkuperäistä.

Laajennuksen voi ottaa myös pois käytöstä väliaikaisesti, sekä asetuksista määritellä kuinka paljon otsikoiden tulee olla harhaanjohtava ennen kuin ne muutetaan.

### Miksi näen edelleen klikkiotsioita?

Selainlaajennus käyttää staattista listaa yksityisyyden suojaamikseksi. Staattisuuden vuoksi lista päivittyy viivellä, eikä aina sisällä uusimpia otsikoita.

Ilmaisversio ei myöskään pysty muuttamaan maksumuurien takana olevia uutisia, joten timattijutut / plus-artikkelit yms. jäävät alkuperäiseksi.

Rajallisten resurssien vuoksi vain yleisimmät ja toivotuimmat sivustot ovat tuettuja. Myöskään sivustot jotka eivät pyri _totuudenmukaiseen_ uutisointii – kuten puoluelehdet – eivät tule olemaan tuettuja.

Selainlaajennus ei myöskään pyri muuttamaan kaikkia otsikoita. Oletuksena pieni puutteellisuus otsikoissa sallitaan. Tätä voi käyttäjä itse säätää, ja halutessaan korvata vaikkapa kaikki tekoälyn tekemällä versiolla, jos tykkää kuivasta otsikoinnista.

On myös mahdollista ettei uutista ja otsikkoa ole arvioitu oikein, tai muodostettu otsikko on vain huono. Tällöin virheelinen otsikko voidaan raportoida käyttäjän toimesta, ja raportoituja otsikoita käytetään parantamaan kielimallin tuottamien otsikoiden laatua.

### Voinko tehdä jotain jos oikaistu otsikko on huonompi kuin alkuperäinen?

Laajennus tarjoaa mahdollisuuden raportoida huonot otsiko-oikaisut. Käyttäjät voivat myös halutessaan ehdottaa parempaa otsikkoa. Raportoitujen otiskoiden oikaisua saatetaan yrittää uudelleen, jos uutinen on edelleen ajankohtainen.

### Kuinka usein uutisotsikoita päivitetään?

Selainlaajennus päivittää listan päällä-ollessaan noin 20min välein. Tämän lisäksi palvelu pyrkii arvioimaan uutisten julkaisun tiheyttä, joten esimerkiksi yöllä lista päivittyy hitaammin kuin päivällä. Tämän vuoksi mahdollisuus nähdä useampia oikaisemattomia otsikoita on suurempi päivällä, mutta pidempi yöllä.

### Mitä maksullinen tilausversio sisältää?

Maksullinen versio sisältää oikaisun myös maksumuurin takana oleviin uutisiin. Maksulla mahdollistetaan Klikkikuri-palvelun pääsy maksullisiin uutisiin.

Lisäksi maksullisen palvelun käyttäjät voivat vaikuttaa suoraan sisällytettävien uutissivustojen listaan äänestämällä.

### Toimiiko Klikkikuri sosiaalisessa mediassa?

Ei toistaiseksi. Joitain agregaattisivuja kuten _Ampparit_ saatetaan tukea tulevaisuudessa, mutta sivustot kuten reddit nojaa klikkiotsikoissa moderaattorien toimintaan.

### Voinko käyttää Klikkikuria mobiililaitteilla?

Selainlaajennus tukee joitan mobiili-selaimia. Uutisten lukemiseen vain mobiiliselain on tuettu, sivustojen omat sovellukset eivät, elleivät ne ole ns. [PWA](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Guides/What_is_a_progressive_web_app) -sovelluksia.

### Seuraako Klikkikuri uutisia joita luen?

Ei. Katso [Yksityisyys](#yksityisyys).

### Tuhoaako kielimalli luonnon?

Ikävä kyllä[^paper-greenai]. Vaikutusten vähentämiseksi Klikkikuri-palvelu pyrkii käyttämään kielimalleja jotka pyörivät uusiutuvalla energialla. Lisäksi tehtävän luoteesta johtuen – pohjimmiltaan tiivistystehtävä – monivaiheiseen ja kattavaan "ajatteluu" ei ole tarvetta[^paper-llm-sum][^paper-sum-bench], ja malleina voidaan käyttää pienempiä ja vähemmän energiaa vieviä malleja.

## Kiitokset

Klikkikurin kehitys on mahdollista kiitos [Jyväskylän Yliopiston](https://www.jyu.fi), [Jyväskylän kaupungin](https://www.jyvaskyla.fi) sekä [Jyväskylän Ammattikorkeakoulun](https://www.jamk.fi) omistaman [Jyväskylän Yritystehtaan myöntämän rahoituksen](https://yritystehdas.fi/tuotekehitysrahoitus) ansiosta. Tehty ❤️ Jyväskylässä.

## Lähteitä
[^chatgpt-policy]: [“Usage Policies.”](https://openai.com/policies/usage-policies/) Openai.com.
[^chatgpt-no-nsfw]: [Model Spec (2024/05/08).](https://cdn.openai.com/spec/model-spec-2024-05-08.html#dont-respond-with-nsfw-content). Openai.com.
[^deepseek-tian]: [“We Tried out DeepSeek. It Worked Well, until We Asked It about Tiananmen Square and Taiwan.”](https://www.theguardian.com/technology/2025/jan/28/we-tried-out-deepseek-it-works-well-until-we-asked-it-about-tiananmen-square-and-taiwan) The Guardian.
[^deepseek-cn-prop]: [“DeepSeek’s Answers Include Chinese Propaganda, Researchers Say.”](https://www.nytimes.com/2025/01/31/technology/deepseek-chinese-propaganda.html) The New York Times.
[^xai-antiwoke]: [“Inside Grok’s War on ‘Woke.’”](https://www.businessinsider.com/xai-grok-training-bias-woke-idealogy-2025-02?op=1) Business Insider.
[^xai-rebel]: [“Elon Musk Announces Grok, a ‘Rebellious’ AI With Few Guardrails.”](https://www.wired.com/story/elon-musk-announces-grok-a-rebellious-ai-without-guardrails/). Wired.
[^paper-greenai]: [“Green AI: Exploring Carbon Footprints, Mitigation Strategies, and Trade Offs in Large Language Model Training.”](https://link.springer.com/article/10.1007/s44163-024-00149-w) Discover Artificial Intelligence.
[^paper-llm-sum]: [“Element-Aware Summarization with Large Language Models: Expert-Aligned Evaluation and Chain-of-Thought Method.”](https://aclanthology.org/2023.acl-long.482/) ArXiv (Cornell University)
[^paper-sum-bench]: [“Benchmarking Large Language Models for News Summarization.”](https://direct.mit.edu/tacl/article/doi/10.1162/tacl_a_00632/119276/Benchmarking-Large-Language-Models-for-News) Transactions of the Association for Computational Linguistics 12 (January): 39–57.
