Tämän viikon aikana olen keskittynyt lähinnä syötteen validointifunktioiden toteuttamiseen. Mietin kuinka voisin toteuttaa validoinnin tehokkaimmin pitäen samalla funktiot riittävän lyhyinä ja selkeinä. Jouduin aluksi tekemään liikaa sisäkkäisiä looppeja, joten päätin kokeilla muuttaa syötteen listaksi kirjaintensa unicode-numeroita. Tällöin pystyin tunnistamaan onko syötteen kirjain numero (0 - 9), pieni kirjain (joista esim. 'log' ja 'max' koostuvat) tai iso kirjain (joita sovellus käyttää muuttujina) sillä perusteella, että osuuko kirjaimen unicode-numero näiden merkkien unicode-numeroiden alueelle. Tämän mahdollistaa se, että näiden merkkien unicode-numerot ovat vierekkäisiä kokonaislukuja, esim. pienet kirjaimet 'a' - 'z' ovat välillä 97 ja 122. Tällöin voin tarkistaa onko merkki pieni kirjain vertaamalla onko sen unicode-numero näiden kahden luvun välissä sen sijaan, että joutuisin esim. tarkistamaan looppaamalla löytyykö merkki stringistä "ab...z" tai Pythonin standardikirjaston tarjoamilla funktioilla, jolloin joutuisin tekemään paljon funktiokutsuja.

Aloin lisäksi toteuttaa funktiota, joka tunnistaa usean merkin numerot (esim. 34) ja funktiot (esim. log, min ja max) syötteestä. Päätin tehdä tämän omassa funktiossaan, jotta shunting yard -funktio voisi keskittyä syötteen elementtien uudelleenjärjestelyyn. En ehtinyt toteuttaa shunting yard -funktiota enkä postfix-notaatiossa olevan syötteen evaluointia, mutta pyrin toteuttamaan ne ensi viikon aikana. Tein docstringit toteutetuille funktioille ja pyrin myös kommentoimaan sovelluksen toimintalogiikkaa ui.py -tiedostossa.

Aloitin yksikkötestien tekemisen toteuttamilleni funktioille. Tällä hetkellä testien kattavuus ei ole kovin hyvä, mutta aion nostaa kattavuutta ensi viikosta lähtien.

Sain sovelluksen graafisen käyttöliittymän melko valmiiksi. Aion vielä toteuttaa määrittelydokumentissa mainitsemani mahdollisuuden muokata syötettä näppäimistön avulla sen sijaan, että syöte pitäisi generoida täysin käyttöliittymän nappien kautta. Tämä siksi, että se mahdollistaa useamman erilaisen virheellisen syötteen antamisen, joita tekemäni validointialgoritmit yrittävät tunnistaa. En halua tässä sovelluksessä estää virheellisiä syötteitä käyttöliittymän avulla, jotta harjoitustyö keskittyisi enemmän algoritmeihin kuin käyttöliittymän toteuttamiseen.

Poistin määrittelydokumentista saadun palautteen perusteella kohdan, missä sanoin vertailevani eri tapoja toteuttaa pino Pythonilla. Palaute liittyi siihen, ettei syötteet tässä sovelluksessa ole tarpeeksi pitkiä, että tehokkuuserot tulisivat ilmi.

Tällä viikolla käytetyt työtunnit: 16