# Udostępnij lokalizację, trasy i punkty — i nawiguj do celu

## Udostępnij swoją aktualną lokalizację

### Szybko

1. Upewnij się, że GPS jest aktywny (przycisk celownika → niebieski trójkąt).
2. Dotknij **niebieskiego trójkąta** na mapie.
3. Panel z Twoimi danymi wysuwa się z góry. Dotknij **Udostępnij**.
4. Wybierz WhatsApp, SMS, e-mail. Wyślij.

### Co pokazuje panel

```
Wysokość 145 m · ±5 m · 19:42
Bateria 87%
ApexGPS: https://apexgps.duttra.de/loc?lat=25.165183&lon=55.409717
Google Maps: https://maps.google.com/?q=25.165183,55.409717
```

- **Wysokość** — metry nad poziomem morza z GPS (pomijana, gdy telefon nie mógł jej ustalić).
- **±dokładność** — pewność GPS w metrach. Drzewa, budynki, głębokie doliny ją zwiększają.
- **Czas** — kiedy pobrano pozycję.
- **Bateria** — aby odbiorca wiedział, czy masz jeszcze zasilanie.
- Dwa **URL-e** — pierwszy otwiera ApexGPS (jeśli zainstalowane), drugi dowolną aplikację map.

### Co widzi odbiorca

Wiadomość zawiera powitanie przed szczegółami:

```
Cześć, to moja aktualna lokalizacja.

Wysokość 145 m · ±5 m · 19:42
Bateria 87%
ApexGPS: https://apexgps.duttra.de/loc?lat=...
Google Maps: https://maps.google.com/?q=...
```

W WhatsApp i podobnych aplikacjach obie URL-e są klikalne. W SMS to tekst do skopiowania.

### Jeśli nie ma jeszcze fixa GPS

Panel się otwiera, ale pokazuje „Szukam GPS…”, a przycisk Udostępnij jest nieaktywny. Gdy pojawi się pierwszy fix, panel się aktualizuje, a Udostępnij aktywuje — nie trzeba zamykać i otwierać.

## Udostępnianie tras i punktów

ApexGPS pozwala wysłać Twoje trasy i punkty komukolwiek jako standardowe pliki `.gpx` — otwórz je w GaiaGPS, Strava, Garmin BaseCamp, wikiloc lub innej kopii ApexGPS. Trzy drogi:

### Pojedyncza trasa lub pojedynczy punkt

- **Trasa** — dotknij trasy na mapie → przycisk **Udostępnij** w panelu. Albo otwórz ekran szczegółów trasy (Trasy → dotknij wiersza) → **ikona udostępniania** w górnym pasku.
- **Punkt** — dotknij punktu na mapie → przycisk **Udostępnij** w panelu. Odbiorca dostaje wiadomość tekstową z nazwą, współrzędnymi, wysokością i dwoma linkami (ApexGPS App Link + Google Maps).

### Grupowe udostępnianie z ekranów listy

Otwórz **menu → Trasy** (lub **Punkty**), przytrzymaj wiersz, aby wejść w tryb zaznaczania, zaznacz interesujące, następnie dotknij **ikony udostępniania** w górnym pasku:

- Trasy → łączy każdą zaznaczoną trasę w jeden plik `.gpx`.
- Punkty → łączy każdy zaznaczony punkt w jeden `.gpx`.

Otwiera się okno udostępniania — wybierz WhatsApp, Drive, Gmail, cokolwiek. Nazwa pliku zawiera datę.

### Udostępnij wszystko widoczne („Udostępnij widoczne")

Najszybsza droga, gdy chcesz komuś przekazać „cały obszar, na który patrzę". Trzy punkty wejścia, wszystkie prowadzą do tego samego arkusza:

- **Ekran mapy → ikona udostępniania** w górnym pasku (po lewej od menu ☰). Używa Twojego aktualnego widoku mapy.
- **menu → Mapy → Udostępnij widoczne trasy i punkty** (trzecia karta w hubie Mapy, pod Pobierz / Zapisane mapy offline). Używa widoku, który miałeś otwarty tuż przed wejściem do huba — możesz więc przewinąć w górę, znaleźć obszar, a potem wskoczyć.
- **Menu kontekstowe ⋮ na mapie → Udostępnij widoczne trasy i punkty**.

Arkusz wysuwa się z listą każdej widocznej trasy (linie przecinające widok ORAZ przełączone jako widoczne) i każdego widocznego punktu (w granicach widoku). Każdy wiersz ma pole — **odznacz, czego nie chcesz wysłać**. Domyślna nazwa pliku jest zgeokodowana ze środka widoku (np. „ApexGPS-Wadi-Bani-Khalid-2026-05-14.gpx", jeśli geokoder zwróci wynik; „ApexGPS-2026-05-14.gpx", jeśli jesteś offline lub geokoder nic nie zwraca).

Dotknij **Udostępnij** → jeden plik `.gpx` zawierający wszystkie zaznaczone trasy + punkty + mały nagłówek metadanych jest budowany, a następnie otwiera się systemowe okno udostępniania.

#### Limity rozmiaru

Paczka „Udostępnij widoczne" jest trzymana w pamięci podczas budowy, więc bardzo duże zaznaczenia mogą się nie powieść z czytelnym komunikatem:

| Limit | Próg |
|---|---|
| Tras na paczkę | 100 |
| Punktów na paczkę | 1 000 |
| Łącznie punktów tras (we wszystkich zaznaczonych) | 100 000 |

Jeśli osiągniesz limit, komunikat powie który — zmniejsz zaznaczenie w arkuszu (odznacz kilka dużych tras), albo użyj **Ustawienia → Dane → Kopia zapasowa** do bardzo dużych eksportów (tamta ścieżka strumieniuje ZIP i nie ma tych limitów).

## Odbieranie udostępnionej lokalizacji

Ktoś wysyła Ci link `apexgps.duttra.de/loc?...`.

### Jeśli masz ApexGPS

Dotknij linku → **ApexGPS otwiera się bezpośrednio**, mapa przesuwa do lokalizacji, pojawia się czerwona celownica. U dołu wysuwa się pasek z trzema przyciskami:

- **Nawiguj** — uruchamia tryb „idź do” (zobacz niżej).
- **Zapisz** — dodaje to miejsce jako punkt (wybierasz nazwę, kolor, symbol).
- **Odrzuć** — usuwa znacznik, nic więcej.

### Jeśli nie masz ApexGPS

Dotknij linku → otwiera się prosta strona z podglądem mapy plus:

- Przycisk **Otwórz w ApexGPS** (tylko Android; proponuje instalację, jeśli aplikacji brak).
- Przycisk **Otwórz w Google Maps**.

## Nawigacja do udostępnionej lokalizacji

Po dotknięciu udostępnionego linku naciśnij **Nawiguj** na dolnym pasku:

- **Jasnoniebieska przerywana linia** rysuje się od Twojej pozycji do celu.
- Pasek zmienia się na: *„Nawiguję · 0,42 km · 045° NE · [Stop]”*.
  - Dystans aktualizuje się przy każdym fixie, na **niebiesko** = auto-aktualizacja.
  - **Kurs** w stopniach + jedna z ośmiu stron świata (N, NE, E, SE, S, SW, W, NW) — idź w tym kierunku.
  - Ten sam dystans pojawia się w **DYST** w pasku statystyk, na niebiesko, podczas nawigacji.
- Gdy znajdziesz się w zasięgu **20 metrów** od celu, nawigacja kończy się automatycznie z „Na miejscu”.
- **Stop** kończy nawigację ręcznie. Celownica pozostaje; możesz **Nawiguj** ponownie lub **Zapisz** jako punkt.

To kurs po linii prostej — bez instrukcji skrętów. W turystyce poza szlakiem to zazwyczaj to, co chcesz; w mieście otwórz raczej link do Google Maps dla trasy ulicami.

### Działa też dla Twoich punktów

Ten sam tryb startuje z dowolnego punktu na mapie. Dotknij punktu → ikona **Nawiguj** (sylwetka idąca) w panelu → panel się zamyka, a pasek nawigacji przejmuje. Szczegóły w [Punkty → Nawigacja do punktu](waypoints.md#nawigacja-do-punktu).

## Kompas nawigacyjny (pełny ekran)

Podczas nawigacji do celu na pasku nawigacji po lewej stronie Stop pojawia się mała **ikona kompasu** 🧭. Dotknij, aby otworzyć pełnoekranowy kompas. Przeciągnij w dół, aby zminimalizować.

### Układ

Górny rząd danych: **Dystans** (niebieski) · **ETA** · **Prędkość** · **Wysokość**.

Centralna analogowa tarcza:
- Zewnętrzny pierścień z kreskami co 15° (większe co 30°).
- Etykiety **N / E / S / W** na karcie.
- Mały **czerwony trójkąt** wskazujący północ rzeczywistą.
- **Niebieska igła** (trójkąt) wskazująca cel w rzeczywistym świecie.
- **Centralny emblemat** pokazujący aktualny kurs telefonu (`245°`) lub literę **S** z napisem *„Symulowany kurs”*, gdy czujnik kompasu jest niepewny (w pobliżu metalu, magnesów, potrzebna kalibracja „ósemką”).

Dolny rząd danych: **Szer · Dł · Kurs° + kardynalny · ±Dokładność**.

Na dole: **Zakończ nawigację** (pełna szerokość, kończy nawigację).

### Użycie

Tarcza **obraca się wraz z orientacją telefonu**, więc czerwony trójkąt zawsze wskazuje rzeczywistą północ, niezależnie od tego, jak trzymasz telefon. Skieruj górę telefonu w kierunku niebieskiej igły, aby stanąć twarzą do celu.

Gdy czujnik jest w pełni wiarygodny, emblemat pokazuje kurs w stopniach; w przeciwnym razie stylizowane „S” i *Symulowany kurs* — przypomnienie, że kierunek może dryfować.

### Co dzieje się z dolnym paskiem statystyk

Gdy kompas jest otwarty, zwykły pasek PRED / WYS / DYST u dołu mapy jest **ukryty** — własny panel kompasu pokazuje już te wartości większymi literami, a duplikacja byłaby zbędna. Pasek wraca, gdy przeciągniesz kompas w dół.

### Co pokazuje pasek nawigacji, gdy kompas jest zamknięty

Gdy kompas jest zminimalizowany, dolny pasek:

> *Nawiguję · **045° NE** · ETA 12 min · 🧭 · Stop*

Kurs i kardynalny są **niebieskie**, bo aktualizują się przy każdym fixie. ETA to szacunek na podstawie aktualnej prędkości — pokazuje `--`, gdy stoisz. Dystans nie jest już na pasku; jest w **DYST** w pasku statystyk (także niebieski podczas nawigacji).

---

**Powiązane:** [Ekran mapy →](map.md) · [Ustawienia →](settings.md) · [FAQ →](faq.md)
