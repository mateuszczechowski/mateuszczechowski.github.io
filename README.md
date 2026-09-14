# mateuszczechowski.github.io

Strona dewelopera i polityka prywatności aplikacji.

To repozytorium jest **korzeniem domeny**, a nie stroną którejkolwiek apki.
Strony i polityki żyją w repozytoriach nazwanych po apkach —
[`pitlane-site`](https://github.com/mateuszczechowski/pitlane-site)
i [`weightfile`](https://github.com/mateuszczechowski/weightfile) — bo tylko
jeden plik naprawdę musi leżeć tutaj.

- `index.html` — rozdroże: lista apek z odnośnikami do ich stron i polityk.
- `privacy.html` — **samo przekierowanie** na
  `pitlane-site/privacy.html`. Zostaje, bo stary adres jest już wpisany
  w AdMobie; skasowanie go zamieniłoby wpis w tamtej konsoli w 404.
- `app-ads.txt` — autoryzacja sprzedawcy reklam (standard IAB). **Musi leżeć
  w korzeniu domeny** i to jest jedyny powód, dla którego ta strona jest
  repozytorium użytkownika, a nie projektu: Pages repo projektu daje adres
  z podkatalogiem, a crawler czyta wyłącznie `https://domena/app-ads.txt`.

  Zweryfikuje się **dopiero po premierze**. Łańcuch zaczyna się od wpisu
  w App Store: crawler bierze stamtąd adres strony dewelopera (pole Marketing
  URL w metadanych wersji) i dopiero pod nim szuka pliku. Dopóki apki nie ma
  w sklepie, nie ma jak powiązać domeny z apką — i z tego samego powodu AdMob
  nie pokazuje jeszcze karty **Apps → app-ads.txt**, bo apka jest tam dodana
  jako „nie ma jej w sklepie".

  Po premierze: ustaw Marketing URL na `https://mateuszczechowski.github.io`
  i dobę później sprawdź status w tej karcie. Gdyby AdMob podał inny
  identyfikator certyfikacji niż `f08c47fec0942fa0`, popraw ostatnie pole —
  reszta linii to publiczny identyfikator wydawcy z App ID.

  Brak tego pliku niczego nie psuje widocznie: ruch jest wtedy
  „nieautoryzowany", część kupujących go pomija i eCPM spada bez żadnego
  komunikatu. Ta sama uwaga dotyczy rozjazdu domen — `www` po jednej stronie
  wystarczy, żeby crawler nie znalazł pliku, a objaw jest identyczny z jego
  brakiem.
