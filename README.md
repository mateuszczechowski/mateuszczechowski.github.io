# mateuszczechowski.github.io

Strona dewelopera i polityka prywatności aplikacji.

- `privacy.html` — polityka prywatności Pit Lane Tycoon (EN + PL).
  Adres podawany w App Store Connect i w AdMobie:
  `https://mateuszczechowski.github.io/privacy.html`
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
