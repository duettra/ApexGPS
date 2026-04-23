# Punkty

**Punkt** to nazwane miejsce na mapie — początek szlaku, szczyt, dobre miejsce na zdjęcie, chata, miejsce postoju samochodu. Każdy ma nazwę, kolor i jeden z 32 symboli.

## Dodawanie punktu

### W konkretnym miejscu (przytrzymanie na mapie)

Przytrzymaj mapę w miejscu, gdzie chcesz punkt. Pojawia się okno z:

- **Nazwa** — opcjonalna. Domyślnie „Punkt”, jeśli puste.
- **Notatki** — opcjonalny opis.
- **Szerokość / Długość** — wypełnione z dotkniętego punktu; **edytowalne**, jeśli chcesz poprawić.
- **Symbol** — wybór z 32 ikon.
- **Kolor** — paleta 16 kolorów.
- **Zapisz** / **Anuluj**.

### Wpisując współrzędne

Otwórz **menu → Punkty** → niebieski FAB **+** w prawym dolnym rogu. To samo okno, ale pola Szer/Dł są puste. Wpisz współrzędne (lub wklej ciąg `lat, lon` w Szerokość — aplikacja rozdzieli automatycznie).

### Z pliku GPX

Otwórz **menu → Punkty** → FAB **niebieski folder** w prawym dolnym rogu. Wybierz jeden lub więcej `.gpx`. Wszystkie punkty z plików zostaną zaimportowane. Duplikaty (ta sama nazwa, w promieniu ~11 m) pomijane automatycznie.

### Na Twojej aktualnej pozycji

Włącz GPS (dotknij celownika, jeśli trójkąt nie jest widoczny), przytrzymaj sam trójkąt (lub bardzo blisko), a okno otworzy się z ustaloną Twoją pozycją.

### Z zaimportowanego GPX (udostępnij / otwórz za pomocą)

Pliki GPX otwarte z innej aplikacji (załącznik WhatsApp, Gmail, menedżer plików) importują także punkty automatycznie. Jeśli punkt nie ma nazwy (niektóre eksportery wpisują współrzędne w pole nazwy), ApexGPS to wykrywa i pokazuje „Punkt”.

## Wyświetlanie punktu

Dotknij dowolnego punktu na mapie. Panel wysuwa się z dołu z:

- Ikona + nazwa.
- Współrzędne (szer/dł z 6 miejsc po przecinku).
- Wysokość (jeśli ustawiona).
- Dystans od Twojej pozycji GPS (niebieski — na żywo).
- Opis (jeśli wpisany).
- Przycisk **Nawiguj** (sylwetka idąca, niebieski) — uruchamia nawigację w linii prostej do punktu. Zobacz niżej.
- Przycisk **Udostępnij** — wysyła punkt przez WhatsApp / SMS / e-mail. Odbiorca dostanie tekst z nazwą, współrzędnymi, wysokością i dwoma linkami (ApexGPS App Link + Google Maps). Jeśli ma ApexGPS, kliknięcie linku otworzy aplikację z czerwoną celownicą w miejscu — może go zapisać jako własny punkt.
- Przycisk **Edytuj**.

Zamknij, przesuwając w dół.

## Nawigacja do punktu

Dotknij ikony **Nawiguj** (sylwetka idąca, kolor podstawowy) w panelu punktu. Panel się zamyka i:

- **Jasnoniebieska przerywana linia** rysuje się od Twojej pozycji GPS do punktu.
- Pasek u dołu staje się: *„Nawiguję · 0,42 km · 045° NE · [Stop]”* — dystans na żywo (niebieski przy autom. aktualizacji), kurs w stopniach + kardynalny (N, NE, E, SE, S, SW, W, NW).
- Pole **DYST** w pasku statystyk również pokazuje ten dystans na niebiesko.
- Automatyczne zatrzymanie przy **20 metrach** od punktu (komunikat „Na miejscu”).
- Dotknij **Stop**, aby zakończyć ręcznie. Punkt pozostaje — dotknij, aby ponownie otworzyć panel.

To ten sam tryb „idź do”, co w przypadku udostępnionych lokalizacji. Kurs w linii prostej, bez instrukcji skrętów — w turystyce poza szlakiem zwykle to, co chcesz.

Dotknij punktu ponownie podczas nawigacji, aby otworzyć panel (nawigacja działa w tle).

## Edycja punktu

Dotknij punktu → **Edytuj** w panelu, lub otwórz **menu → Punkty** i dotknij wiersza.

To samo okno co przy dodawaniu. Nazwa, Notatki, **Szerokość**, **Długość**, Symbol, Kolor są edytowalne. Przy zapisie aplikacja waliduje współrzędne (szer ∈ [−90, 90], dł ∈ [−180, 180], muszą być liczbami) i pokazuje czerwony błąd inline, jeśli poza zakresem.

## Przesuwanie punktu

**Przytrzymanie i przeciągnięcie** punktu na mapie. Przeciągnij na nową pozycję. Po puszczeniu u dołu pojawia się pasek:

- **Przenieś** — potwierdza nową pozycję.
- **Anuluj** — wraca do poprzedniej.

Nic nie jest zapisywane, dopóki nie naciśniesz Przenieś. Przydatne, jeśli przeciągnięcie było przypadkowe.

## 32 symbole

Pogrupowane według przeznaczenia, aby łatwo przeglądać w wybieraczu:

| Grupa | Symbole |
|---|---|
| **Nawigacja / ogólne** | Flaga · Miejsce · Gwiazda · Ulubione |
| **Natura / turystyka** | Szczyt · Przełęcz · Punkt widokowy · Zdjęcie · Las · Źródło · Wodospad · Woda pitna · Biwak · Schronisko · Miejsce piknikowe · Drogowskaz · Ruiny |
| **Informacyjne** | Info · Ostrzeżenie |
| **Usługi** | Parking · Paliwo · Restauracja · Hotel · Szpital · Toalety |
| **Transport** | Samochód · Rower · Pieszo · Pociąg · Łódź · Samolot · Gaz |

Wszystkie 32 można wybrać przy dodawaniu lub edycji. Symbol zapisuje się z punktem i przetrwa eksport → ponowny import.

## Lista punktów (menu → Punkty)

Wszystkie punkty, licznik w tytule.

### Filtrowanie

**Ikona filtra** → dwie sekcje:

- **Kolor** — dotknij kolor, aby pokazać tylko ten. **Wszystkie**, aby wyczyścić.
- **Symbol** — przewijana lista wszystkich 32 symboli z ikonami. Dotknij, aby filtrować.

Aktywne filtry → ikona niebieska.

### Sortowanie

**Ikona sortowania**:

- **Najnowsze** — wg daty importu / utworzenia (domyślnie).
- **Wg nazwy** — alfabetycznie.
- **Najbliższe** — najbliżej Twojej pozycji GPS. „(brak GPS)” jeśli brak zapamiętanej pozycji.

### Wyszukiwanie

Wpisz w pole, aby filtrować punkty, których nazwa LUB opis zawiera Twój tekst.

### Zaznaczanie wielu

Przytrzymaj punkt na liście → tryb zaznaczania. Zaznacz więcej, potem grupowe usuwanie. Nie ma (jeszcze) grupowej zmiany koloru/symbolu dla punktów — użyj Edytuj dla każdego.

### Usuń duplikaty

Jeśli ponownie importowałeś ten sam GPX w starszych wersjach, możesz mieć zduplikowane punkty (ta sama nazwa na tych samych współrzędnych). Dotknij **⋮** → **Usuń duplikaty**. Zachowuje najstarszą kopię i usuwa resztę; pokazuje, ile usunięto.

## Usuwanie

Pojedynczo: przeciągnij / dotknij ikony kosza w wierszu lub przycisk Usuń w oknie edycji.

Wiele: tryb zaznaczania + grupowe usuwanie.

Brak cofania. [Kopia zapasowa](backup.md) na wszelki wypadek.

## Wyświetlanie punktu na mapie

Z listy dotknij punktu → aplikacja wraca do mapy i przesuwa ją do punktu. Śledzenie wstrzymane, aby nowy fix GPS nie nadpisał od razu.

---

**Powiązane:** [Trasy →](tracks.md) · [Kopia zapasowa →](backup.md) · [Ekran mapy →](map.md)
