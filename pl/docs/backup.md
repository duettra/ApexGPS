# Kopia zapasowa i przywracanie

ApexGPS przechowuje wszystko **lokalnie na Twoim telefonie**. Nie ma synchronizacji z chmurą. Jeśli przywrócisz fabryczne ustawienia, zmienisz telefon lub odinstalujesz aplikację, **Twoje trasy, punkty i regiony offline są stracone**, chyba że zrobiłeś kopię zapasową.

Kopia zapasowa jest ręczna, ale łatwa. Rób ją okresowo, jeśli masz dane, których nie chcesz stracić.

## Co zawiera kopia

- **Wszystkie trasy** (dane GPX, nazwa, kolor, widoczność).
- **Wszystkie punkty** (nazwa, opis, współrzędne, wysokość, kolor, symbol).
- **Wszystkie zapisane regiony map offline** (paczki kafelków — mogą być duże).
- **Wszystkie ustawienia** (motyw, domyślne źródło, grubość trasy, rozmiar punktów, blokada obrotu).

Czego **nie ma** w kopii:

- **Pamięć podręczna przeglądania** (kafelki auto-zapisywane z codziennego użytku). Nieuwzględniana, bo łatwa do odtworzenia i potencjalnie ogromna. Zapisane regiony offline są w kopii; podręczna nie.
- **Klucz API Thunderforest** jest w kopii razem z ustawieniami, więc nie trzeba go ponownie wpisywać.

## Tworzenie kopii

1. **Menu → Ustawienia → Dane → Kopia zapasowa**.
2. Opcjonalnie: odznacz kategorie, których nie chcesz (zapisane mapy są największe — pomiń, jeśli chcesz tylko trasy/punkty).
3. Dotknij **Utwórz kopię**.
4. Plik ZIP trafia do prywatnej pamięci aplikacji. Otwiera się okno udostępniania — wybierz gdzie:
   - **Google Drive / Dropbox / OneDrive** — kopia w chmurze.
   - **Wyślij do siebie** e-mailem / czatem.
   - **Zapisz do Pobranych** przez menedżer plików.

Plik ZIP nazywa się np. `apexgps-backup-2026-04-19.zip`. Data w nazwie.

**Utworzenie kopii z zapisanymi regionami offline może zająć minutę lub dwie** i daje duży ZIP (50–500 MB w zależności od liczby regionów). Interfejs pokazuje postęp.

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
