# Ekran mapy

Wszystko kręci się wokół tego widoku. Oto do czego służy każdy element.

## Gesty

| Gest | Efekt |
|---|---|
| Przeciągnięcie jednym palcem | Przesuwanie mapy. |
| Szczypnięcie | Przybliżanie / oddalanie. |
| Obrót dwoma palcami | Obrót mapy. |
| Dotknięcie trasy | Otwiera panel trasy (profil, pasek przewijania). |
| Dotknięcie punktu | Otwiera panel punktu (nazwa, opis, edycja). |
| Dotknięcie niebieskiego trójkąta (Twoja pozycja) | Otwiera panel **Udostępnij lokalizację**. |
| Przytrzymanie na pustej mapie | Dodaje punkt w tym miejscu. |

## Prawy górny róg: kompas

Okrągły znaczek z czerwoną igłą. Zawsze widoczny. Igła zawsze wskazuje północ rzeczywistą, niezależnie od obrotu mapy — działa też jako stały wskaźnik północy.

- **Dotknięcie** — płynnie obraca mapę do pozycji „północ u góry”.
- **Przytrzymanie** — przełącza blokadę obrotu. Znaczek **niebieski** = dwupalcowe gesty obrotu są ignorowane; mapa zachowuje orientację. Przytrzymaj ponownie, aby odblokować.

Opcja blokady przy starcie w **Ustawienia → Wygląd → Zablokuj obrót przy starcie** dla tych, którzy nie chcą obracać mapy.

## Prawa kolumna: przyciski akcji

Od góry do dołu:

### Mierz dystans
**Ikona linijki**. Dotknij, aby wejść w tryb pomiaru; dotykaj mapy, aby stawiać punkty; linia je łączy, a pasek u dołu pokazuje łączny dystans. Przeciągnij pierwszy punkt na swoją pozycję GPS, aby mierzyć „od siebie”. Dotknij ikonki ponownie, aby wyjść.

### Warstwy mapy
**Ikona warstw**. Sześć stylów: OpenTopoMap (domyślny, turystyczny), OSM Standard (czysta mapa ogólna), ESRI Topo, ESRI relief cieniowany, Satelita, Outdoors (Thunderforest — wymaga darmowego klucza API w Ustawienia → Klucze API).

Wybrany styl jest zapamiętywany między sesjami.

### Śledź mnie (celownik)
Trzy stany — kolor przycisku mówi, który:

| Stan | Kolor | Zachowanie |
|---|---|---|
| **Wyłączony** | Szary | GPS wyłączony, brak trójkąta na mapie. |
| **Włączony, zablokowany** | Niebieski wypełniony | GPS aktywny, trójkąt widoczny, mapa co kilka sekund centruje się na Tobie. |
| **Włączony, odblokowany** | Blady niebieski | GPS aktywny, trójkąt aktualizuje się, ale mapa pozostaje tam, gdzie ją przesunąłeś. |

- Dotknięcie z **Wyłączony** → włącza GPS + blokuje kamerę na Tobie.
- Dotknięcie z **Zablokowany** → wyłącza GPS.
- **Przeciągnięcie mapy** w stanie zablokowanym → automatycznie przechodzi w odblokowany. Trójkąt się aktualizuje; mapa stoi.
- Dotknięcie z **Odblokowany** → centruje + ponownie blokuje.
- **Przytrzymanie** w dowolnym aktywnym stanie → natychmiastowo wyłącza GPS (pomija animację centrowania).

### Gdzie jest przycisk importu (+)?

Od **v1.25.2** mapa nie ma już dedykowanego FAB importu — import GPX znajduje się na ekranach listy Tras i Punktów. Zobacz [Trasy](tracks.md#importowanie) lub [Punkty](waypoints.md#dodawanie-punktu).

## Lewy górny róg

- **☰ menu** — szuflada nawigacji (Trasy, Punkty, Mapy, Ustawienia).
- **Znaczek nagrywania** — czerwona kropka w ciemnym kółku. Dotknij, aby rozpocząć nagrywanie aktualnej wędrówki. Podczas nagrywania rozszerza się do stopera na żywo `00:00:00`; dotknij stopera, aby otworzyć **Pauza / Zakończ / Usuń**. Twoja trasa rysuje się jako czerwona linia na mapie w miarę przemieszczania się. Po **Zakończ** nagranie zostaje zapisane jako nowa Trasa, a panel otwiera się, żebyś mógł od razu przejrzeć wynik. Zobacz [Trasy → Nagrywanie](tracks.md#nagrywanie).

## Dolny pasek statystyk

Trzy wartości:

- **PRED** — aktualna prędkość km/h z GPS.
- **WYS** — aktualna wysokość w metrach.
- **DYST** — zależne od kontekstu:
  - W **trybie pomiaru**: łączna długość linii.
  - Podczas **nawigacji do udostępnionej lokalizacji**: dystans na żywo do celu (niebieski przy automatycznej aktualizacji).
  - W przeciwnym razie: pusty.

## Wskaźnik offline

Gdy urządzenie nie ma zasięgu, u góry pojawia się mały czerwony znaczek **„Offline”**. Kafelki z pamięci podręcznej nadal się wyświetlają; niewidzianych wcześniej kafelków nie załaduje, dopóki nie wrócisz online. Zobacz [Mapy offline](offline-maps.md), aby pobrać regiony wcześniej.

---

**Powiązane:** [Trasy →](tracks.md) · [Punkty →](waypoints.md) · [Udostępnij lokalizację →](share-and-navigate.md)
