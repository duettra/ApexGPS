# Ustawienia

**Menu → Ustawienia** jest zorganizowane w cztery podekrany: Wygląd, Pamięć, Dane, Klucze API. Każdy ma przycisk ⓘ obok tytułów sekcji, wyjaśniający funkcję.

## Wygląd

### Motyw
- **System** (domyślnie) — podąża za jasnym/ciemnym ustawieniem telefonu.
- **Jasny** — zawsze jasny.
- **Ciemny** — zawsze ciemny.

### Domyślna mapa
Styl używany przy uruchomieniu. Sześć opcji; zobacz [Ekran mapy → Warstwy mapy](map.md) po szczegóły. Styl można zmieniać w trakcie sesji przyciskiem warstw.

### Szerokość linii trasy
Suwak, 4–24 dp. Grubsze linie są bardziej widoczne, gdy wiele tras się nakłada; cieńsze wyglądają czyściej przy wysokim zoomie. Domyślnie ~6 dp.

### Rozmiar punktów
Mały / Normalny / Duży / XL. To mnożnik nakładany na automatyczny rozmiar adaptowalny do zoomu — markery kurczą się przy niskim zoomie i rosną przy wysokim, aby pozostać czytelne; to ustawienie przesuwa całą skalę. Domyślnie Normalny (1,0×).

### Zablokuj obrót przy starcie
- **Wył.** (domyślnie) — dwupalcowe gesty obrotu działają od otwarcia aplikacji.
- **Wł.** — obrót zablokowany przy uruchomieniu; przytrzymaj kompas, aby odblokować. Przydatne, jeśli często przypadkowo obracasz mapę.

## Pamięć

### Użycie pamięci podręcznej
Łączny rozmiar pamięci przeglądania + podział wg źródła.

### Wyczyść pamięć
- **Wyczyść wszystko** — usuwa kafelki z pamięci dla każdego stylu. NIE usuwa zapisanych regionów offline.
- **Wyczyść [źródło]** — tylko dla danego stylu. Przydatne, gdy jeden styl zajmuje dużo (satelita > mapa poziomic).

Pamięć podręczna przeglądania odbudowuje się, gdy patrzysz na obszary z zasięgiem. Wyczyszczenie nie dotyka danych jawnie zapisanych w hubie Mapy.

## Dane

### Kopia zapasowa
Tworzy ZIP z trasami, punktami, zapisanymi regionami i ustawieniami. Przełączniki pozwalają wyłączyć kategorie (regiony są największe — często pomijane dla szybkich kopii „tylko moje trasy”). Zobacz [Kopia zapasowa](backup.md).

### Przywróć
Otwiera istniejący plik `apexgps-backup-*.zip`. Wybierz **Scal** (dodaj do istniejących) lub **Zamień** (nadpisz). Zobacz [Kopia → Scal vs Zamień](backup.md#scalanie-vs-zamiana).

### Optymalizuj wszystkie trasy
Uruchamia Douglas-Peucker na każdej zaimportowanej trasie. Redukuje liczbę punktów bez widocznej zmiany kształtu. Przydatne, gdy zaimportowałeś dużo bardzo szczegółowych GPX-ów i mapa działa wolno na starym telefonie. Pokazuje łączną liczbę dotkniętych.

Pojedyncze trasy można też optymalizować jednocześnie z ekranu szczegółów.

### Wczytaj dane przykładowe
Importuje 3 punkty (Szczyt / Punkt widokowy / Początek szlaku) i 3 trasy o różnych długościach i profilach wysokości (5 km / 12 km / 25 km, z podejściami od +260 m do +3030 m). Przydatne do odkrywania aplikacji bez własnych plików GPX. Po imporcie to zwykłe trasy/punkty — usuń je kiedy chcesz.

## Klucze API

### Thunderforest
Wymagany dla stylu **Outdoors (Thunderforest)**. Darmowy plan „Hobby”: 150 000 żądań miesięcznie, bez karty. Zarejestruj się na [thunderforest.com](https://www.thunderforest.com/), skopiuj klucz API, wklej tutaj → **Zapisz**.

Bez klucza styl Outdoors pokazuje placeholder; pozostałe pięć stylów działa bez klucza.

## Informacje

**Ustawienia → Informacje** pokazuje wersję, atrybucje i e-mail kontaktowy — dodatkowo **Podręcznik użytkownika**: dotykalne wpisy dla każdego rozdziału tej dokumentacji, dostarczone w aplikacji, aby cały przewodnik działał offline. Dotknij rozdziału → otwiera się czytnik i renderuje rozdział w aplikacji. Linki między rozdziałami są honorowane; strzałka wstecz wraca do listy. Link **„Czytaj online”** u dołu otwiera tę samą dokumentację na [apexgps.duttra.de/docs](https://apexgps.duttra.de/docs/) w przeglądarce. Po pomoc: [sandwalker.one@proton.me](mailto:sandwalker.one@proton.me).

---

**Powiązane:** [FAQ →](faq.md) · [Kopia zapasowa →](backup.md)
