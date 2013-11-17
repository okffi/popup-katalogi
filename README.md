Popup-katalogi
==============

Popup-katalogin pohjimmainen idea on hostata dataa GitHubissa [Simple Data Format (SDF) -formaatissa](http://data.okfn.org/standards/simple-data-format) ja generoida SDF-paketeista katalogi-näkymä, jota käyttäjät voivat selata github.io-domainin kautta.

Katalogi-näkymän voi tuottaa monella tavalla. Jos halutaa, että katalogi-näkymä päivittyy automaattisesti, kun jonkin yksittäisen popup-katalogin repoon otetaan dataa vastaa pull requestilla, täytyy selvittää, onko mahdollista hyödyntää GitHubin uumenissa pyörivää [Jekyll-kirjastoa](http://jekyllrb.com/), jota käytetään repojen sisällön tarjoiluun github.io-domainin kautta. Normaalisti Jekyll generoi sivuston [YAML:illa metadatoitetuista Markdown-tiedostoista](http://jekyllrb.com/docs/frontmatter/). Nyt sivusto generoitaisiin Markdownien sijaan SDF-pakettien kansioista ja niiden sisältämistä JSON-tiedostoista.

Jos kelpuutetaan ratkaisu, jossa popup-katalogin ylläpitäjä päivittää katalogin manuaalisesti ajamalla dataa sisältävän pull-requestin jälkeen sivuston generointi-skriptin omalla koneellaan, on vaihtoehtoja valtavasti. Voidaan Jekyllin sijaan käyttää jotakin muuta sivustogeneraattoria, kuten vaikkapa mielenkiintoisen oloista [Harp:ia](http://harpjs.com/). Ultra-kevyt ja yksinkertainen vaihtoehto olisi tehdä [Grunt-skripti](http://gruntjs.com/), joka koostaa kansiollisesta SDF-paketteja agregoidun JSON-tiedoston. Tällöin katalogi olisi mahdollista generoida kokonaan JavaScriptillä käyttäjän selaimessa, esimerkiksi jQuerylla tai Angular:illa lataamalla agregoitu JSON-selaimeen.

Voi olla, että popup-katalogissa voisi käyttää GitHubin jatkuvasti kehittyviä [CSV:n esittämiskykyjä](https://github.com/blog/1601-see-your-csvs). Senkin voisi tosin tehdä kokonaan käyttäjän selaimessa jollakin sopivalla js-kirjastolla.
