# Trasy

**Trasa** to zarejestrowana droga — sekwencja punktów GPS połączonych linią na mapie. Trasy możesz uzyskać albo **nagrywając** je na żywo w ApexGPS, albo **importując** pliki GPX (z GaiaGPS, Strava, Garmin Connect, wikiloc.com lub dowolnego innego eksportera GPX).

## Nagrywanie

Dotknij czerwonej **kropki nagrywania** w lewym górnym rogu mapy. Kropka rozszerza się do chipa z czasem na żywo (`00:12:43`), a czerwona linia okruchów zaczyna rysować Twoją wędrówkę na mapie, gdy napływają nowe punkty GPS.

### Podczas nagrywania

- **Dotknij chipa stopera**, aby wyświetlić menu:
  - **Pauza** — zatrzymuje zegar; nowe punkty nie są dodawane do linii, dopóki nie dotkniesz **Wznów**.
  - **Zakończ** — zapisuje wędrówkę jako nową Trasę, otwiera panel trasy, abyś mógł od razu zobaczyć statystyki + profil wysokości.
  - **Usuń** — odrzuca bieżące nagranie bez zapisu.
- Pierwszoplanowa usługa GPS uruchamia się sama, gdy rozpoczynasz nagrywanie — nie musisz wcześniej włączać śledzenia.
- **Ekran wyłączony?** Aplikacja zmniejsza częstotliwość aktualizacji GPS, żeby oszczędzać baterię (≈10 s między punktami przy wyłączonym ekranie vs 2 s przy włączonym). Żadne działanie nie jest wymagane — przełącza się automatycznie.

### Jeśli lokalizacja systemowa jest wyłączona

Dotknięcie nagrywania, gdy systemowy przełącznik lokalizacji Androida jest wyłączony, pokazuje krótki komunikat *„Lokalizacja systemowa jest wyłączona — włącz, aby nagrywać"* ze skrótem do **Ustawienia**. Nagrywanie się nie rozpoczyna.

### Jeśli aplikacja zostanie zabita w trakcie wędrówki

Jeśli Android zabije aplikację podczas aktywnego nagrywania (odzyskiwanie pamięci, wymuszenie zatrzymania, restart), linia zebrana do tego momentu zostaje **zachowana**. Otwórz aplikację ponownie, a chip wraca, pokazując upływający czas w stanie pauzy — dotknij **Wznów**, aby kontynuować, lub **Zakończ**, aby zapisać to, co masz.

### Typ aktywności

Każda nagrana trasa startuje z tagiem **Wędrówka**. Otwórz ekran szczegółów trasy (Trasy → dotknij wiersza) i użyj listy rozwijanej **Aktywność**, aby zmienić na Spacer / Bieganie / Kolarstwo / Off-road / Paralotniarstwo. Zaimportowane trasy domyślnie nie mają tagu aktywności; możesz przypisać go w ten sam sposób.

### Przycinanie nagrania

Szum rozgrzewki GPS na początku trasy? Zapomniałeś dotknąć **Zakończ** i trasa ciągnie się aż do auta? Otwórz ekran szczegółów trasy i dotknij **Przytnij trasę**:

- Otwiera się okno z mini-podglądem mapy całej trasy i profilem wysokości poniżej.
- Przeciągnij dwa uchwyty na wykresie wysokości, aby ustawić początek i koniec zakresu, który chcesz zachować. Mini-mapa aktualizuje się na żywo — zachowywany odcinek pozostaje w kolorze trasy, odrzucane fragmenty stają się szare.
- Wskaźnik **Zachowano** pokazuje wynikowy dystans i liczbę punktów.
- Dotknij **Przytnij**, aby zatwierdzić. Okno potwierdzenia mówi dokładnie, ile punktów zniknie z każdego końca. **Nie można tego cofnąć** — zachowaj eksport GPX, jeśli masz wątpliwości.

Przycinanie przelicza też dystans, bounding box i profil wysokości trasy, tak że statystyki u góry ekranu natychmiast odzwierciedlają skróconą trasę.

## Importowanie

### Z pliku

Otwórz **menu → Trasy** → dotknij niebieskiego **FAB z folderem** w prawym dolnym rogu. Wybierz jeden lub więcej plików `.gpx` z pamięci telefonu (wielokrotny wybór dozwolony). Aplikacja wróci do mapy i automatycznie dopasuje zoom do zaimportowanych tras.

### Z udostępnienia (WhatsApp, e-mail, inna aplikacja)

Ktoś wysyła Ci plik `.gpx`? Dotknij go w czacie / e-mailu / menedżerze plików → system zaproponuje otwarcie w ApexGPS → aplikacja automatycznie zaimportuje i przejdzie do mapy.

### Co jest importowane

- Linie trasy (z wysokością, jeśli GPX ją zawiera).
- Wszystkie punkty zapisane w pliku GPX (każdy z nazwą, opisem, symbolem zmapowanym na najbliższy odpowiednik ApexGPS).

**Ochrona przed duplikatami:** przy ponownym imporcie tego samego GPX punkty o identycznych współrzędnych nie są dodawane ponownie. Linie trasy SĄ importowane ponownie (o tej samej nazwie, duplikat można usunąć ręcznie).

## Wyświetlanie trasy na mapie

Dotknij linii trasy na mapie. Panel wysuwa się z dołu z:

- Nazwa + dystans.
- **Profil wysokości** — mały wykres. Przesuń palcem po nim, aby przejść wzdłuż trasy; wskaźnik pokazuje odpowiedni punkt na mapie.
- **Podejście / zejście** łącznie.
- Przycisk **Edytuj** → otwiera szczegóły trasy.
- Przycisk **Udostępnij** → eksportuje trasę jako `.gpx`.
- Przycisk **Ukryj** → minimalizuje panel do wąskiego paska u dołu (aby pracować dalej z wybraną trasą, nie zasłaniając mapy).
- **Zamknij** (przeciągnięcie w dół) → zamyka panel.

## Lista tras (menu → Trasy)

Pełna lista wszystkich zaimportowanych tras. Licznik w tytule.

### Filtrowanie

Dotknij **ikony filtra**. Dwie opcje:

- **Widoczność** — Wszystkie / Tylko widoczne / Tylko ukryte. Ukryte trasy pozostają na liście, ale nie są rysowane.
- **Kolor** — paleta 16 kolorów. Dotknij koloru, aby zobaczyć tylko trasy w tym kolorze.

Aktywny filtr → ikona na niebiesko. Dotknij **Wszystkie** w którejś sekcji, aby wyczyścić.

### Sortowanie

Dotknij **ikony sortowania**:

- **Najnowsze** — wg daty importu (domyślnie).
- **Wg nazwy** — alfabetycznie.
- **Najbliższe** — punkt środkowy najbliżej Ciebie. Korzysta z ostatniej znanej pozycji GPS telefonu, więc działa nawet bez aktywnego GPS w tej sesji. „(brak GPS)” jeśli uprawnienie odmówione lub brak zapamiętanej pozycji.
- **Wg punktów** — trasy z największą liczbą punktów pierwsze (przydatne przy wyłapywaniu bardzo szczegółowych tras).

### Wyszukiwanie

Wpisz w pole wyszukiwania, aby filtrować trasy, których nazwa zawiera Twój tekst.

### Zaznaczanie wielu

Przytrzymaj trasę → tryb zaznaczania. Zaznacz interesujące, następnie:

- **Grupowa zmiana koloru** (ikona palety) — jeden kolor dla wszystkich zaznaczonych.
- **Grupowe pokazywanie / ukrywanie** (ikony oka) — szybka widoczność.
- **Grupowe usuwanie** (czerwony kosz) — z potwierdzeniem.
- **Zaznacz wszystkie** — zaznacza wszystkie trasy w filtrowanym widoku.

## Akcje dla pojedynczej trasy

Dotknij trasy na liście → otwiera ekran **Szczegóły**.

- **Nazwa** — edytowalna.
- **Kolor** — dotknij, aby otworzyć wybieracz.
- **Widoczność** — pokaż / ukryj na mapie.
- **Profil wysokości** — ten sam wykres co w panelu mapy, ale w pełnym rozmiarze.
- **Podejście / zejście** łącznie.
- **Liczba punktów** — ile punktów GPS składa się na trasę.
- **Pokaż na mapie** — zamyka szczegóły i dopasowuje zoom do trasy.
- **Optymalizuj** — upraszcza, usuwając nadmiarowe punkty. Przydatne przy masowych importach. Nieodwracalne dla trasy; ponowny import z pliku daje oryginał.
- **Udostępnij jako GPX** — to samo co przycisk udostępniania w panelu mapy.
- **Usuń** — z potwierdzeniem.

## Optymalizacja masowa (duże biblioteki)

Jeśli zaimportowałeś wiele bardzo gęstych tras, mapa może działać powoli na starszych telefonach. **Ustawienia → Dane → Optymalizuj wszystkie** uruchamia to samo uproszczenie dla wszystkich tras. Interfejs pokazuje, ile będzie dotkniętych.

## Usuwanie

Pojedynczo: przeciągnięcie / dotknięcie ikony kosza w wierszu lub przycisk Usuń w ekranie szczegółów.

Wiele: tryb zaznaczania + grupowe usuwanie.

Brak cofania. Zrób [kopię zapasową](backup.md), jeśli masz wątpliwości.

---

**Powiązane:** [Punkty →](waypoints.md) · [Ekran mapy →](map.md) · [Kopia zapasowa →](backup.md)
