# Kopia zapasowa i przywracanie

ApexGPS przechowuje wszystko **lokalnie na Twoim telefonie**. Nie ma synchronizacji z chmurą. Jeśli przywrócisz fabryczne ustawienia, zmienisz telefon lub odinstalujesz aplikację, **Twoje trasy, punkty i regiony offline są stracone**, chyba że zrobiłeś kopię zapasową.

Kopia zapasowa jest ręczna, ale łatwa. Rób ją okresowo, jeśli masz dane, których nie chcesz stracić.

## Co zawiera kopia

- **Wszystkie trasy** (dane GPX, nazwa, kolor, widoczność, tag aktywności).
- **Wszystkie punkty** (nazwa, opis, współrzędne, wysokość, kolor, symbol).
- **Wszystkie zapisane regiony map offline** — zobacz [Przepis vs pełne kafelki](#przepis-vs-pe%C5%82ne-kafelki) niżej, są dwa sposoby ich zapisania.
- **Wszystkie ustawienia** (motyw, domyślne źródło, grubość trasy, rozmiar punktów, blokada obrotu, oszczędzanie baterii itd.).

Czego **nie ma** w kopii:

- **Pamięć podręczna przeglądania** (kafelki auto-zapisywane z codziennego użytku). Nieuwzględniana, bo łatwa do odtworzenia i potencjalnie ogromna.
- **Klucz API Thunderforest** jest w kopii razem z ustawieniami, więc nie trzeba go ponownie wpisywać.

## Tworzenie kopii

1. **Menu → Ustawienia → Dane → Kopia zapasowa**.
2. Wybierz, co dołączyć — są pola dla tras / punktów / ustawień, plus **trójstopniowy selektor dla zapisanych regionów map offline** (zobacz niżej).
3. Dotknij **Utwórz kopię**.
4. Plik ZIP trafia do prywatnej pamięci aplikacji. Otwiera się okno udostępniania — wybierz gdzie:
   - **Google Drive / Dropbox / OneDrive** — kopia w chmurze.
   - **Wyślij do siebie** e-mailem / czatem.
   - **Zapisz do Pobranych** przez menedżer plików.

Plik ZIP nazywa się np. `apexgps-backup-2026-05-14.zip`. Data w nazwie.

### Przepis vs pełne kafelki

Dla zapisanych regionów map offline wybierasz **jeden z trzech trybów**:

| Tryb | Rozmiar | Zachowanie | Między platformami? |
|---|---|---|---|
| **Nie dołączaj** | najmniejszy | Wiersze regionów nie są w ogóle zapisywane. | n/d |
| **Przepis** | ~80 KB łącznie | Każdy region jest zapisany jako krótka „karta instrukcji" — nazwa, ramka, zakres zoomu, źródło kafelków. Po przywróceniu regiony pojawiają się w **Mapy → Zapisane mapy offline** oznaczone *„Jeszcze nie pobrano · X kafelków"*, z przyciskiem **Pobierz** do sprowadzenia faktycznych kafelków z serwera. | **Tak** — działa między Androidem a iOS. |
| **Pełne kafelki** | 50–500 MB | Surowa paczka MBTiles każdego regionu jest osadzona w ZIP-ie. Po przywróceniu regiony są od razu używalne offline; ponowne pobieranie nie jest potrzebne. | **Tylko Android.** iOS nie umie (jeszcze) czytać osadzonych paczek. |

**Wybierz Przepis** dla przenosin między urządzeniami (wymiana telefonu, dzielenie kopii ze znajomym na iOS, kopia „na wszelki wypadek" trzymana na Drive na zawsze). Ponowne pobranie jest szybkie po Wi-Fi i korzysta z najbardziej aktualnych kafelków.

**Wybierz Pełne kafelki**, jeśli specjalnie chcesz jednoetapowej kopii przywracalnej offline tylko na Androidzie — przydatne przed wyjazdem, gdzie możesz wyczyścić telefon i nie mieć Wi-Fi w celu.

**Utworzenie kopii w trybie Pełne kafelki może zająć minutę lub dwie** i daje duży ZIP. Interfejs pokazuje postęp.

## Przywracanie kopii

### Prosta droga

Dotknij pliku `apexgps-backup-*.zip` w dowolnym menedżerze plików / Google Drive / załączniku Gmail. Android zaproponuje aplikacje do otwarcia; wybierz ApexGPS. Aplikacja otwiera się bezpośrednio na Ustawienia → Dane z oknem przywracania.

### Przez Ustawienia

1. **Menu → Ustawienia → Dane → Przywróć**.
2. Wybierz ZIP z wybieraka.
3. Wybierz tryb (zobacz niżej).
4. Potwierdź.

### Scalanie vs Zamiana

Oba tryby przetwarzają ZIP kategoria po kategorii.

| Tryb | Co się dzieje |
|---|---|
| **Scal** | Nowe elementy z kopii są DODAWANE do tego, co już masz. Trasy o tej samej nazwie nie są łączone — mogą powstać duplikaty; wyczyść przez **Ustawienia → Dane → Optymalizuj wszystkie** lub usuń pojedynczo. |
| **Zamień** | Każda kategoria z kopii ZASTĘPUJE to, co masz obecnie. Jeśli kopia zawiera trasy, wszystkie istniejące są najpierw usuwane. Kategorie odznaczone przy tworzeniu kopii NIE są ruszane przy przywracaniu. |

**Praktyczna reguła:**

- Nowy telefon → **Zamień** (chcesz dokładny stan ze starego).
- Bierzesz zestaw punktów z kopii znajomego → **Scal** (zachowaj swoje dane, dodaj jego).

Przywracanie działa strumieniowo — szybkie nawet dla kilkusetmegabajtowego ZIP-a. Jeśli przerwie się w trakcie, częściowe kategorie mogły zostać zastosowane; uruchom ponownie dla pewności.

### Przywracanie z trybu przepisu — pobranie regionów

Jeśli kopia używała trybu **Przepis** dla map offline, przywracanie jest natychmiastowe, ale w **Mapy → Zapisane mapy offline** zobaczysz regiony oznaczone *„Jeszcze nie pobrano · X kafelków"* z przyciskiem **Pobierz**. Dotknij go, aby ponownie sprowadzić kafelki z serwera. Jeśli region używa kafelków Thunderforest, a nie wkleiłeś jeszcze klucza API, aplikacja pokaże jednorazowy komunikat informujący, że trzeba go najpierw dodać w **Ustawienia → Klucze API**; gdy klucz jest na miejscu, stuknij Pobierz ponownie.

### Przywracanie między wersjami aplikacji

Kopia v2 (utworzona na tej wersji lub nowszej) odmawia otwarcia na starszych wersjach aplikacji i pokazuje *„Format kopii v2 jest nowszy niż wspiera ta aplikacja. Zaktualizuj ApexGPS."* — najpierw zaktualizuj, potem przywróć. Starsze kopie v1 nadal się przywracają na obecnej wersji bez dodatkowego kroku.

## Przeniesienie na nowy telefon

1. **Na starym:** utwórz kopię ze wszystkim zaznaczonym. Wyślij sobie e-mailem / zapisz na Drive.
2. **Na nowym:** zainstaluj ApexGPS, otwórz, nadaj uprawnienia, zaloguj się do e-maila / Drive.
3. **Pobierz ZIP** na nowy telefon, dotknij → przywróć z **Zamień**.

Gotowe. Trasy, punkty, zapisane mapy i ustawienia są na miejscu.

## Ochrona przed reset fabrycznym / odinstalowaniem

Auto-kopia Androida przywraca *część* ustawień (motyw, domyślne źródło, klucz API, grubość trasy, rozmiar punktów, blokada obrotu) z Google Drive przy reinstalacji. To NIE obejmuje tras, punktów ani regionów — tylko lekkie preferencje.

**Jedyny niezawodny sposób na zachowanie danych turystycznych przez reinstalację to kopia ZIP.** Zrób ją przed każdą zmianą telefonu lub większą aktualizacją systemu.

---

**Powiązane:** [Ustawienia →](settings.md) · [Trasy →](tracks.md) · [Punkty →](waypoints.md)
