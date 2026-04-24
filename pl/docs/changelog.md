# Historia zmian

Zmiany widoczne dla użytkownika, najnowsze u góry. Refaktory wewnętrzne / podbicia wersji są w prywatnym repo.

---

## 1.29.0 — 24 kwi 2026

- **Nagrywanie trasy na żywo.** Dotknij czerwonej kropki w lewym górnym rogu mapy, aby rozpocząć nagrywanie bieżącej wędrówki. Stoper na żywo `HH:MM:SS` zastępuje kropkę; dotknij go, aby uzyskać **Pauza / Zakończ / Usuń**. Twoja trasa rysuje się jako czerwona linia, gdy się poruszasz. Po **Zakończ** nagranie zostaje zapisane jako nowa Trasa, a panel otwiera się automatycznie, abyś mógł od razu sprawdzić dystans, podejście i profil wysokości.
- **Przytnij trasę.** Na ekranie szczegółów trasy **Przytnij trasę** otwiera okno z mini-podglądem mapy i dwoma przeciąganymi uchwytami na wykresie wysokości. Obetnij zły początek (jeszcze bez fixa GPS) lub przypadkowy ogon (zapomniałeś dotknąć Zakończ) bez utraty reszty trasy. Destrukcyjne — krok potwierdzenia mówi dokładnie, ile punktów stracisz.
- **Tag aktywności na trasę.** Ekran Szczegóły trasy ma nową listę **Aktywność**: Wędrówka · Spacer · Bieganie · Kolarstwo · Off-road · Paralotniarstwo. Nagrania domyślnie są Wędrówką; zaimportowane trasy startują bez tagu.
- **Wysokość punktu.** Okno edycji punktu ma nowe opcjonalne pole **Wysokość (m)** — uzupełnij, gdy chcesz nieść wysokość dla znanego szczytu / przełęczy / itp. Puste = brak zapisanej wysokości (tak jak dziś zaimportowane punkty bez danych wysokości).
- **Odświeżone szczegóły trasy + edycja punktu.** Zgrupowane karty, nagłówki sekcji, ikony w każdym wierszu, ikona właściwa dla aktywności na chipie Aktywność, przycisk **Usuń** z czerwoną obwódką pasujący do destrukcyjnego działania, nowa statystyka **Punkty** na ekranie trasy. Edycja punktu jest bardziej zwarta — cały formularz mieści się teraz nad systemowym paskiem nawigacji na większości telefonów bez przewijania.
- **Odzyskiwanie po śmierci procesu.** Jeśli Android zabije aplikację w trakcie nagrywania (mało pamięci, wymuszenie zatrzymania), linia jest zachowana. Otwórz aplikację ponownie, a nagranie wraca w stanie pauzy — wznów, zakończ lub odrzuć.
- **Oszczędzanie baterii: adaptacyjna częstotliwość GPS.** Podczas nagrywania przy wyłączonym ekranie częstotliwość aktualizacji GPS spada z 2 s do 10 s, by oszczędzać baterię. Gdy odblokujesz telefon, wraca do 2 s dla płynności. W pełni automatyczne.
- **Zabezpieczenie lokalizacji systemowej.** Dotknięcie nagrywania, gdy systemowy przełącznik lokalizacji Androida jest wyłączony, pokazuje teraz komunikat ze skrótem do **Ustawienia** zamiast cicho uruchamiać martwe nagranie.
- **Wskazówka no-fix.** Jeśli dotkniesz nagrywania, zanim GPS pozyska pierwszy punkt, krótki komunikat *„Szukam GPS…"* wyjaśnia, dlaczego linia się jeszcze nie zaczęła. Nagrywanie rusza, gdy tylko pojawi się pierwszy fix.
- **Usunięte:** opcjonalny przycisk alarmowy. Obszar w lewym górnym rogu należy teraz do znaczka nagrywania.

---

## 1.28.0 — 24 kwi 2026

- **Dodano arabski.** العربية dołącza do niemieckiego, francuskiego, hiszpańskiego i polskiego obok angielskiego. Sześć języków interfejsu w **Ustawienia → Wygląd → Język**.
- **Panel punktu teraz przetłumaczony.** Dotknięcie punktu pokazywało wcześniej „Elev 145 m · Dist 0,42 km" po angielsku — niezależnie od języka aplikacji. Teraz zmienia się z nim (np. „Wys 145 m · Dyst 0,42 km").
- **Liczby pozostają w cyfrach zachodnich we wszystkich językach.** Współrzędne, dystanse, wysokości, kursy — zawsze `25.165`, `145`, `0.42`. Spójne z Google Maps / WhatsApp.

---

## 1.27.0 — 23 kwi 2026

- **Pięć języków interfejsu.** Niemiecki, francuski, hiszpański, polski i angielski. Wybierz w **Ustawienia → Wygląd → Język**, lub „Język systemu" aby podążać za telefonem.
- **Podręcznik offline w Twoim języku.** Wszystkie 11 rozdziałów (Ustawienia → Informacje → Podręcznik) jest przetłumaczonych.
- **Język przetrwa przywracanie z kopii.** Wybrany język jest w ZIP-ie.
- **Pasek statystyk również przetłumaczony.** PRED / WYS / DYST zmieniają się z językiem.

---

## 1.26.2 — 22 kwi 2026

- **Klucz API Thunderforest szyfrowany w spoczynku.** Klucz wklejany w **Ustawienia → Zaawansowane** trafia teraz do magazynu opartego na Android Keystore, a nie do zwykłego tekstu. Istniejące klucze migrują automatycznie przy pierwszym uruchomieniu. Kopie zawierające ustawienia nadal niosą klucz w ZIP-ie (potrzebny dla przenośności) — nowe czerwone ostrzeżenie w oknie kopii o tym przypomina.
- **Bezpieczniejsze przywracanie.** Przywracanie odrzuca teraz ZIP-y z próbą traversalu katalogu, ogranicza wpisy do 100 000, rozmiar wpisu do 500 MB i łączny rozmiar rozpakowany do 2 GB. Spreparowane / błędne kopie nie mogą już zapełnić pamięci ani wyjść z katalogu kopii.
- **Przycisk Anuluj w kopii.** Podczas trwającej kopii można dotknąć **Anuluj** pod przyciskiem zajętości, aby przerwać bez czekania.
- **Postęp importu GPX.** Snackbar „Importuję GPX…” podczas dużych importów — aplikacja nie wydaje się już zawieszona.
- **Usługa lokalizacji pewniejsza na Androidzie 14+.** Usługa pierwszoplanowa GPS uruchamia się poprawnie na Androidzie 14 i 15 (wcześniej w niektórych przypadkach była cicho zabijana). Zawężony zasięg wake-locka — powinien poprawić zużycie baterii przy długich sesjach.
- **Naprawa podglądu kafelków + higiena tła.** Podgląd w szczegółach zapisanej mapy offline ładuje się bez blokowania UI. Wewnętrznie: usługa pobierania kafelków nie może już ANR-ować przy zamykaniu. Buildy release nie przeciekają już logów debug.
- **Usunięto:** link „Buy-me-a-coffee” w Ustawienia → Informacje. ApexGPS pozostaje darmowy bez reklam, śledzenia i chmury.
- **Wewnętrzne (dla ciekawskich):** Room ma teraz jawne migracje (1→2→3); aktualizacje zachowują trasy i punkty, nawet gdy schemat się zmienia. Wipe przy downgrade pozostaje — sideloadowanie starszego APK na nowszy resetuje bazę.

---

## 1.26.1 — 22 kwi 2026

- **Podgląd szczegółów mapy offline — poprawiony skos.** Podgląd w **Menu → Zapisane mapy offline → [dotknij regionu]** malował kafelki poza własnymi granicami, nachodząc na wiersze statystyk i przycisk „Pokaż na mapie”. Teraz poprawnie przycina się do prostokąta 1,6:1.
- **Link „Czytaj online” w aplikacji** w Ustawienia → Informacje wskazuje teraz na `apexgps.duttra.de/docs/` (wyrenderowany przewodnik) zamiast surowego widoku drzewa GitHub.
- **Buy me a coffee.** Nowa sekcja Wsparcie w **Ustawienia → Informacje**. ApexGPS zostaje darmowy bez reklam i śledzenia — jeśli jest Ci użyteczny, niewielki napiwek pomaga rozwijać nowe funkcje.

---

## 1.26.0 — 21 kwi 2026

- **Podręcznik offline.** Pełny 10-rozdziałowy podręcznik jest teraz zawarty w aplikacji — otwórz **Ustawienia → Informacje** i dotknij rozdziału, aby czytać bez internetu. Linki między rozdziałami działają w aplikacji; zewnętrzne otwierają przeglądarkę.
- **Wczytaj dane przykładowe.** Nowy przycisk w **Ustawienia → Dane** ładuje 3 punkty (Szczyt / Punkt widokowy / Początek szlaku) i 3 trasy różnej długości i profilu wysokości. Aby poznać aplikację bez własnych GPX-ów. Po imporcie są to normalne trasy/punkty — usuwalne później.
- **Nawiguj automatycznie włącza GPS.** Dotknięcie Nawiguj przy udostępnionej lokalizacji lub punkcie włącza teraz automatycznie lokalizację na żywo, jeśli była wyłączona. Koniec zawieszania „Szukam GPS…”, gdy faktycznie chcesz nawigować.
- **Przesuwanie mapy znów odblokuje śledzenie.** Regresja z wcześniejszych buildów 1.2x: pod ciągłymi aktualizacjami GPS mapa wracała do Twojej pozycji co sekundę, nawet po przeciągnięciu. Przeciągnij mapę → kamera się odblokuje (FAB średnio-niebieski) jak wcześniej; trójkąt nadal się aktualizuje w miejscu.
- **Symbole punktów, które crashowały.** Import GPX z symbolami Punkt widokowy / Przełęcz / Wodospad / Miejsce piknikowe / Woda pitna / Drogowskaz / Ruiny / Toalety mógł crashnąć aplikację przy renderowaniu. Naprawione — wszystkie 32 symbole renderują się teraz poprawnie.

---

## 1.25.x — 21 kwi 2026

- **Import GPX z listy Tras** (ikona folderu w prawym górnym rogu). To samo z listy Punktów. FAB importu na mapie znika — import jest teraz w ekranach list.
- **Dodaj punkt wg współrzędnych** — niebieski „+” na liście Punktów otwiera pełne okno edycji z pustymi polami Szer/Dł. Wpisz współrzędne lub wklej ciąg `lat, lon` w Szerokość (automatyczne rozdzielenie).
- **Edytuj współrzędne punktu.** Szer i Dł są teraz edytowalne w oknie edycji z walidacją inline (szer ∈ [-90, 90], dł ∈ [-180, 180]).
- **FAB Śledź mnie przeniesiony na dół** prawej kolumny mapy — najbliżej kciuka. Warstwy wyżej, Mierz jeszcze wyżej.

---

## 1.24.x — 19 kwi 2026

- **Pełnoekranowy kompas nawigacyjny.** Podczas nawigacji do celu dotknij 🧭 na pasku, aby otworzyć duży analogowy kompas: dystans / ETA / prędkość / wysokość u góry, obracająca się tarcza z niebieską igłą wskazującą cel, szer/dł/kurs/dokładność na dole. Przeciągnij w dół, aby zminimalizować. Zobacz [Udostępnij → Kompas](share-and-navigate.md#kompas-nawigacyjny-pełny-ekran).
- **Udostępnij punkt.** Panel punktu ma teraz przycisk Udostępnij obok Nawiguj i Edytuj. Wysyła punkt przez dowolną aplikację; odbiorcy z ApexGPS otwierają link bezpośrednio jako udostępnioną lokalizację, którą mogą Zapisać.
- **Czystszy pasek nawigacji + pasek statystyk.** Pasek nawigacji pokazuje teraz kurs + ETA (kurs na niebiesko — aktualizuje się), dystans jest w polu DYST paska statystyk. Koniec duplikatów.
- Igła kompasu elegancko emerging z centralnego emblematu (subtelne szlifowanie wizualne).

## 1.23.0 — 19 kwi 2026

- **Nawiguj do dowolnego punktu** bezpośrednio z panelu punktu. Dotknij ikonki idącej sylwetki obok Edytuj — ta sama jasnoniebieska przerywana linia + dystans/kurs na żywo + auto-stop przy 20 m co przy nawigacji udostępnionej lokalizacji. Zobacz [Punkty → Nawigacja do punktu](waypoints.md#nawigacja-do-punktu).

## 1.22.2 — 19 kwi 2026

- **Link do podręcznika** w Ustawienia → Informacje. Otwiera tę dokumentację w przeglądarce.

## 1.21.0 — 19 kwi 2026

- **Śledź mnie: swobodne przesuwanie.** Przeciąganie mapy nie walczy już z GPS — trójkąt nadal się aktualizuje, ale mapa pozostaje tam, gdzie ją umieścisz. Dotknij przycisku, aby wycentrować ponownie. Przytrzymaj, aby od razu wyłączyć GPS. Trzy widoczne stany (wył / zablokowany / odblokowany).
- **Kompas do północy animowany** zamiast skakać. Mniej gwałtowny powrót do północy.

## 1.20.0 — 19 kwi 2026

- **Nawiguj do udostępnionej lokalizacji.** Gdy ktoś udostępnia Ci lokalizację przez link `apexgps.duttra.de`, dotknij Nawiguj w dolnym pasku, aby narysować jasnoniebieską przerywaną linię od Twojej pozycji do jego z dystansem i kursem na żywo. Auto-stop przy 20 m. Zobacz [Udostępnij → Nawigacja do udostępnionej lokalizacji](share-and-navigate.md#nawigacja-do-udostępnionej-lokalizacji).
- **Wizualna wskazówka dla udostępnionych lokalizacji.** Czerwona celownica pojawia się w udostępnionym miejscu, abyś dokładnie widział, gdzie jest na mapie. [Zapisz] jako punkt lub [Odrzuć], aby wyczyścić.

## 1.19.0 — 19 kwi 2026

- **Lista Punktów: filtr + sortowanie.** Filtruj według koloru lub symbolu, sortuj wg daty / nazwy / najbliższe. Tak samo jak przy Trasach. Zobacz [Punkty → Lista punktów](waypoints.md#lista-punktów-menu--punkty).
- **Format udostępnianej wiadomości czystszy** — etykietowane URL-e (`ApexGPS:` / `Google Maps:`) z pustą linią powyżej.

## 1.18.x — 19 kwi 2026

- **Udostępnij swoją aktualną lokalizację.** Dotknij niebieskiego trójkąta → panel info z wysokością, dokładnością, czasem, baterią → Udostępnij przez WhatsApp, SMS, e-mail itp. Pełny przepływ w [Udostępnij i nawiguj](share-and-navigate.md).
- **App Links.** Lokalizacje udostępnione z ApexGPS otwierają aplikację bezpośrednio na urządzeniach, które ją mają, z czerwonym markerem.
- **Fallback web** — jeśli odbiorca nie ma ApexGPS, link otwiera stronę z podglądem mapy + przyciskiem Google Maps.

## 1.17.6 — 18 kwi 2026

- **Hub Mapy** przeprojektowany. Pobieranie nowego obszaru i przeglądanie zapisanych map offline żyją teraz na jednym ekranie jako rozwijane karty. Zobacz [Mapy offline](offline-maps.md).
- Naprawa czarnych rogów przy obrocie (bez czarnych trójkątów po bokach).

## 1.16.0 — 17 kwi 2026

- **Ustawienia** zreorganizowane w podekrany (Wygląd / Pamięć / Dane / Klucze API / Informacje) z pomocą inline.
- Ustawienie **Rozmiar punktów** (Mały / Normalny / Duży / XL) w Wyglądzie.
- **Blokada obrotu przy starcie** — dla nienawidzących przypadkowych obrotów.

## 1.15.0 i wcześniejsze

- Rdzeń aplikacji: import GPX, lista tras, punkty z 32 symbolami, pobieranie map offline, kompas + obrót, mierzenie dystansu, kopia/przywracanie do ZIP, optymalizacja tras.

---

*Po szczegóły na poziomie raportów o błędach lub kontekst deweloperski: [prywatne repo](mailto:sandwalker.one@proton.me) — skontaktuj się z deweloperem o dostęp.*
