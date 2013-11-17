Helsingin kaupungin tietojärjestelmäluettelot CSV-muodossa
==========================================================

Helsingin kaupunki on julkaissut Excel-tiedoston, jossa on osin puutteellinen, mutta paras saatavilla oleva luettelo kaupunkiorganisaation käyttämistä tietojärjestelmistä. Alkuperäistiedostossa järjestelmät on lueteltu virastoittain taulukon välilehdillä. Aineiston käytettävyyden parantamiseksi erilliset luettelot on koottu yhdeksi CSV-tiedostoksi (luettelossa 1040 riviä), jonka metatiedot on muvattu erillisessä tiedostossa.

* [Alkuperäinen Excel -muotoinen tietojärjestelmäluettelo](https://dl.dropboxusercontent.com/u/2949803/Opendata/HKI_tietojarjestelmaluettelo_nettiversio_muokattu.xlsx)
* Tietojärjestelmäluettelo CSV-muodossa: [HKI_tietojarjestelmaluettelo_nettiversio_muokattu.csv](https://github.com/okffi/popup-katalogi/blob/master/HKI_tietojarjestelmaluettelo_nettiversio_muokattu.csv)
* CSV -muotoisen tietojärjestelmäluettelon metatiedot: [datapackage.json](https://github.com/okffi/popup-katalogi/blob/master/datapackage.json)
* [Näkymä, jossa luettelosta on automaattisesti generoitu katalogi-näkymä: [bit.ly/helsingin_tietojarjestelmaluettelo](http://bit.ly/helsingin_tietojarjestelmaluettelo)

Helsingin tietojärjestelmäluettelo toimii esimerkkiaineistona, jonka avulla kehitetään helppoa tapaa päivittää ja esittää luettelodataa GitHubissa.


Popup-katalogi
==============
Toinen käyttötarkoitus CSV-muotoisen datan GitHub -pohjaiseen päivittämiseen on luoda kaupungeille helppo Popup-datakatalogi.

Popup-katalogin pohjimmainen idea on hostata dataa GitHubissa [Simple Data Format (SDF) -formaatissa](http://data.okfn.org/standards/simple-data-format) ja generoida SDF-paketeista katalogi-näkymä, jota käyttäjät voivat selata github.io-domainin kautta.

Katalogi-näkymän voi tuottaa monella tavalla. Jos halutaa, että katalogi-näkymä päivittyy automaattisesti, kun jonkin yksittäisen popup-katalogin repoon otetaan dataa vastaa pull requestilla, täytyy selvittää, onko mahdollista hyödyntää GitHubin uumenissa pyörivää [Jekyll-kirjastoa](http://jekyllrb.com/), jota käytetään repojen sisällön tarjoiluun github.io-domainin kautta. Normaalisti Jekyll generoi sivuston [YAML:illa metadatoitetuista Markdown-tiedostoista](http://jekyllrb.com/docs/frontmatter/). Nyt sivusto generoitaisiin Markdownien sijaan SDF-pakettien kansioista ja niiden sisältämistä JSON-tiedostoista.

Jos kelpuutetaan ratkaisu, jossa popup-katalogin ylläpitäjä päivittää katalogin manuaalisesti ajamalla dataa sisältävän pull-requestin jälkeen sivuston generointi-skriptin omalla koneellaan, on vaihtoehtoja valtavasti. Voidaan Jekyllin sijaan käyttää jotakin muuta sivustogeneraattoria, kuten vaikkapa mielenkiintoisen oloista [Harp:ia](http://harpjs.com/). Ultra-kevyt ja yksinkertainen vaihtoehto olisi tehdä [Grunt-skripti](http://gruntjs.com/), joka koostaa kansiollisesta SDF-paketteja agregoidun JSON-tiedoston. Tällöin katalogi olisi mahdollista generoida kokonaan JavaScriptillä käyttäjän selaimessa, esimerkiksi jQuerylla tai Angular:illa lataamalla agregoitu JSON-selaimeen.

Voi olla, että popup-katalogissa voisi käyttää GitHubin jatkuvasti kehittyviä [CSV:n esittämiskykyjä](https://github.com/blog/1601-see-your-csvs). Senkin voisi tosin tehdä kokonaan käyttäjän selaimessa jollakin sopivalla js-kirjastolla.
