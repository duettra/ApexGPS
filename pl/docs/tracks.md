# Trasy

**Trasa** to zarejestrowana droga — sekwencja punktów GPS połączonych linią na mapie. Trasy pochodzą z importu plików GPX (z GaiaGPS, Strava, Garmin Connect, wikiloc.com lub dowolnego innego eksportera GPX).

**Uwaga:** ApexGPS w tej wersji nie zapisuje nowych tras. Nagrywanie na żywo jest planowane na przyszłą wersję.

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
