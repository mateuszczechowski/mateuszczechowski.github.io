# mateuszczechowski.github.io

Strona dewelopera i polityka prywatności aplikacji.

To repozytorium jest **korzeniem domeny**, a nie stroną którejkolwiek apki.
Strony i polityki żyją w repozytoriach nazwanych po apkach —
[`pitlane-site`](https://github.com/mateuszczechowski/pitlane-site),
[`weightfile`](https://github.com/mateuszczechowski/weightfile),
[`targetcounter-privacy`](https://github.com/mateuszczechowski/targetcounter-privacy)
i [`sticta-support`](https://github.com/mateuszczechowski/sticta-support);
Intimoment ma własną domenę, intimoment.com — bo tylko
jeden plik naprawdę musi leżeć tutaj.

- `index.html` — portfolio: apki jako kolekcjonerskie karty (paleta i Young
  Serif ze Sticty), z linkami do App Store, stron i polityk, plus X i LinkedIn.
  Ikony w `assets/` to kopie z App Store (`itunes.apple.com/lookup`), a
  `sticta.png` z repo `sticta-support`. Nowa apka = nowa karta w `.deck`
  i przenumerowanie „No. xx / yy”.
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
