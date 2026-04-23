# FAQ i rozwiązywanie problemów

## „Mój niebieski trójkąt się nie pokazuje”

Trzy możliwe przyczyny:

1. **GPS wyłączony.** Dotknij przycisku celownika w prawej kolumnie. Przechodzi z szarego na niebieski. Zobacz [Ekran mapy → Śledź mnie](map.md#śledź-mnie-celownik).
2. **Uprawnienie do lokalizacji nieudzielone.** Wejdź w Ustawienia telefonu → Aplikacje → ApexGPS → Uprawnienia → Lokalizacja → **Zezwól tylko podczas używania aplikacji**, lokalizacja **Dokładna**. Następnie otwórz ApexGPS ponownie.
3. **Brak fixa GPS.** W pomieszczeniu, przy wysokich budynkach lub w głębokich dolinach pierwsze pobranie może trwać 30 s lub dłużej. Wyjdź na zewnątrz, jeśli to możliwe.

## „Mapa ciągle wraca do mojej pozycji co kilka sekund”

To zablokowane śledzenie. Przeciągnij mapę raz — przycisk celownika zmienia się na jaśniejszy niebieski i mapa zostaje tam, gdzie ją umieścisz. Trójkąt nadal się aktualizuje; tylko kamera przestaje Cię gonić. Aby wycentrować: dotknij celownika.

Zobacz [Ekran mapy → Śledź mnie](map.md#śledź-mnie-celownik).

## „Jak całkowicie wyłączyć GPS?”

**Przytrzymaj** przycisk celownika. GPS się zatrzymuje, trójkąt znika, bateria oszczędzona.

Dotknięcie przełączające ze stanu zablokowanego też wyłącza, ale przytrzymanie pomija animację centrowania — przydatne, gdy oddaliłeś się i nie chcesz, aby mapa skoczyła z powrotem przed wyłączeniem.

## „Ktoś wysłał mi link lokalizacji — jak go otworzyć?”

Jeśli link wygląda jak `https://apexgps.duttra.de/loc?lat=...&lon=...`, dotknij go bezpośrednio z wiadomości. Z zainstalowanym ApexGPS otworzy się w aplikacji z czerwoną celownicą. Bez ApexGPS otworzy się strona internetowa z podglądem mapy + linkiem do instalacji.

Inne typy linków mapowych (URL-e Google Maps itp.) otwierają dowolną preferowaną aplikację map — nie wiążą się z ApexGPS.

Zobacz [Udostępnij → Odbieranie udostępnionej lokalizacji](share-and-navigate.md#odbieranie-udostępnionej-lokalizacji).

## „Czy mogę nagrać nową trasę podczas wędrówki?”

W tej wersji nie. Nagrywanie na żywo (Twojej drogi podczas marszu) jest planowane na przyszłą wersję. Obecnie trasy pochodzą z importu plików GPX (Twoich z innej aplikacji lub od kogoś innego).

## „Ile miejsca zajmuje aplikacja?”

Sama aplikacja jest mała (~10 MB). Pamięć rośnie z powodu:

- **Pamięci podręcznej przeglądania** — kafelków obszarów, na które patrzyłeś. Zobacz **Ustawienia → Pamięć**.
- **Zapisanych regionów offline** — kafelków pobranych wstępnie przez hub Mapy. Mogą być duże (50–500 MB na region zależnie od zoomów).
- **Tras + punktów** — malutkich, zwykle <1 MB nawet przy setkach.

Czyść pamięć przez Ustawienia → Pamięć → Wyczyść. Usuwaj regiony przez hub Mapy → dotknij region → Usuń.

## „Mapa działa wolno przy zoomie / przesuwaniu”

Kilka rzeczy do sprawdzenia:

1. **Zbyt wiele wczytanych tras.** Lista Tras → filtr widoczności → ukryj te, których dziś nie używasz. Lub masowo usuń stare importy.
2. **Bardzo szczegółowe trasy.** **Ustawienia → Dane → Optymalizuj wszystkie** — liczba punktów spada ~90 % bez widocznej zmiany.
3. **Niski zoom z wieloma punktami.** Punkty grupują się automatycznie przy niskim zoomie (pojedyncza kropka z licznikiem) — dotknij klastra, aby się przybliżyć. Jeśli telefon nadal ma problem, próg klastrowania jest stały w kodzie; rozważ ukrycie tras.
4. **Stary telefon.** ApexGPS celuje w nowoczesnego Androida. Przy urządzeniach sprzed 2020 r. spadki wydajności są nieuniknione z 500+ trasami na ekranie.

## „Nie widzę nowej wersji w Play Store”

Jesteś testerem zamkniętym i zostałeś powiadomiony o aktualizacji. Jeśli się nie pojawia:

1. Play Store → ikona profilu (prawy górny) → **Zarządzaj aplikacjami i urządzeniem** → **Dostępne aktualizacje** → odśwież. Jeśli ApexGPS się pojawi, dotknij **Aktualizuj**.
2. Nadal nic? Otwórz ponownie link zaproszenia testera. Następnie wymuś zatrzymanie Play Store, otwórz ponownie, wyszukaj ApexGPS.
3. Nadal nic? **Ustawienia → Aplikacje → Google Play Store → Pamięć → Wyczyść pamięć podręczną**. Otwórz ponownie Play Store, wyszukaj.
4. CDN Google zajmuje 2–24 godziny po „auto-publikacji”. Jeśli właśnie się dowiedziałeś, poczekaj kilka godzin.

## „Czy mogę używać ApexGPS bez udzielania uprawnienia do lokalizacji?”

W dużej mierze tak. Możesz importować GPX, przeglądać trasy, planować, mierzyć dystanse, zarządzać punktami i pobierać regiony mapy — wszystko bez lokalizacji. Co tracisz:

- Trójkąt pozycji na żywo.
- Śledzenie / sortowanie „najbliższe”.
- Funkcję Udostępnij lokalizację (nie ma lokalizacji do udostępnienia).
- Nawigację do celu (brak „Ciebie” do narysowania linii).

## „Czy aplikacja wysyła moją lokalizację gdzieś?”

Nie. ApexGPS nie wykonuje żądań sieciowych z Twoją lokalizacją. Jedyna wychodząca aktywność sieciowa to pobieranie kafelków mapy, nierozróżnialne od przeglądania mapy — serwery kafelków widzą IP + współrzędne kafelków, nic o Tobie. Zobacz [politykę prywatności](/privacy.html).

Udostępnianie przez przycisk Udostępnij jest całkowicie inicjowane przez użytkownika — Ty wybierasz aplikację (WhatsApp itd.) i odbiorcę.

## „Telefon znajomego z Androidem otwiera udostępniony link w przeglądarce, nie w ApexGPS”

Link otwiera się bezpośrednio w ApexGPS tylko na urządzeniach, gdzie weryfikacja App Links od Google się powiodła. Świeże instalacje czasem potrzebują pierwszego uruchomienia aplikacji, zanim weryfikacja zacznie działać. Poproś znajomego:

1. Otworzyć ApexGPS raz, udzielić uprawnienia do lokalizacji, zamknąć.
2. Ponownie dotknąć Twojego udostępnionego linku.

Teraz powinno się otworzyć bezpośrednio w aplikacji. Jeśli nadal otwiera w przeglądarce, Android może proponować selektor — może wybrać „Zawsze otwieraj w ApexGPS”.

## „Czy mogę przywrócić kopię ApexGPS na iPhonie?”

Nie. ApexGPS jest tylko na Androida. Format kopii jest specyficzny dla aplikacji.

## „Gdzie są fizycznie moje dane?”

Na Twoim telefonie, w prywatnej pamięci aplikacji ApexGPS (`/data/data/com.apexgps.app/` z dostępem root — bez tego niedostępne). Trasy + punkty w bazie SQLite; ustawienia w pliku preferencji; kafelki jako pliki obrazów na dysku.

Nic nie jest nigdzie wysyłane. Do kopii użyj [Kopii zapasowej](backup.md).

---

**Nadal utknięty?** [sandwalker.one@proton.me](mailto:sandwalker.one@proton.me) — raporty o błędach mile widziane.
