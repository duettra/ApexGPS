# Ustawienia

**Menu → Ustawienia** jest zorganizowane w pięć podekranów: Wygląd, Pamięć, Dane, Klucze API, Zaawansowane. Każdy ma przycisk ⓘ obok tytułów sekcji, wyjaśniający funkcję.

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

### Rozmiar pamięci kafli mapy
Wybierz, ile miejsca na dysku przeznaczyć na automatyczny cache kafli mapy: **250 MB**, **500 MB** (domyślny), **1 GB**, **2 GB**. Nowy limit zaczyna działać natychmiast przy następnym pobraniu kafla — restart aplikacji nie jest potrzebny. Zapisane regiony offline są przechowywane osobno i nie wliczają się do tego limitu; zmiana rozmiaru cache\'u nigdy nie usuwa regionu, który świadomie pobrałeś.

### Wyczyść pamięć
- **Wyczyść wszystko** — usuwa kafelki z pamięci dla każdego stylu. NIE usuwa zapisanych regionów offline.
- **Wyczyść [źródło]** — tylko dla danego stylu. Przydatne, gdy jeden styl zajmuje dużo (satelita > mapa poziomic).

Pamięć podręczna przeglądania odbudowuje się, gdy patrzysz na obszary z zasięgiem. Wyczyszczenie nie dotyka danych jawnie zapisanych w hubie Mapy.

## Dane

### Kopia zapasowa
Tworzy ZIP z trasami, punktami, zapisanymi regionami offline i ustawieniami. Przełączniki pozwalają wyłączyć kategorie. Zapisane regiony offline mają **trójstopniowy tryb**: **Nie dołączaj** (pomiń je) / **Przepis** (mały — tylko instrukcje pobrania każdego regionu, działa między Androidem a iOS) / **Pełne kafelki** (stare zachowanie — osadza surowe paczki kafelków, duże, ale przywracalne offline, tylko Android). Zobacz [Kopia zapasowa](backup.md).

### Przywróć
Otwiera istniejący plik `apexgps-backup-*.zip`. Wybierz **Scal** (dodaj do istniejących) lub **Zamień** (nadpisz). Zobacz [Kopia → Scal vs Zamień](backup.md#scalanie-vs-zamiana).

### Optymalizuj wszystkie trasy
Uruchamia Douglas-Peucker na każdej zaimportowanej trasie. Redukuje liczbę punktów bez widocznej zmiany kształtu. Przydatne, gdy zaimportowałeś dużo bardzo szczegółowych GPX-ów i mapa działa wolno na starym telefonie. Pokazuje łączną liczbę dotkniętych.

Pojedyncze trasy można też optymalizować jednocześnie z ekranu szczegółów.

### Wczytaj dane przykładowe
Prawdziwy zapis **trawersowania Watzmanna** (Berchtesgaden, Niemcy): Wimbachbrücke → Watzmannhaus → Hocheck → Mittelspitze → Südspitze → Wimbachgrieshütte → Wimbachbrücke, pętla ~22,6 km / +2250 m / około 10–12 h marszu. Trzy punkty orientacyjne we współrzędnych rzeczywistych: początek Wimbachbrücke (628 m), schronisko DAV Watzmannhaus (1930 m), Watzmann-Mittelspitze (*Hauptgipfel*, 2713 m). Importowane automatycznie przy pierwszym uruchomieniu nowej instalacji; ten przycisk importuje je ponownie na żądanie, jeśli je usunąłeś i chcesz mieć je z powrotem. Po imporcie to zwykłe trasy/punkty — usuń je kiedy chcesz.

## Klucze API

### Thunderforest
Wymagany dla stylu **Outdoors (Thunderforest)**. Darmowy plan „Hobby”: 150 000 żądań miesięcznie, bez karty. Zarejestruj się na [thunderforest.com](https://www.thunderforest.com/), skopiuj klucz API, wklej tutaj → **Zapisz**.

**Bez klucza styl Outdoors jest ukryty** w selektorze stylu mapy (oraz w selektorze pobierania regionu offline), aby przez przypadek go nie wybrać i nie zobaczyć fallbacku OpenTopoMap. Wklej klucz → pozycja wraca natychmiast w obu menu. Pozostałe pięć stylów działa bez klucza.

## Zaawansowane

### Oszczędzanie baterii przy wysokiej prędkości
Gdy poruszasz się szybciej niż **36 km/h** (≈22 mph) — samochodem, pociągiem, szybkim e-bike’em — aplikacja zmniejsza częstotliwość próbkowania GPS do jednego fixu co **10 sekund** zamiast jednego na sekundę. Trasy o kształcie drogi nadal nagrywają się czysto; dokładność pasa ruchu jest zredukowana podczas jazdy. Wycina mniej więcej połowę zużycia GPS-a na autostradowym odcinku podróży bez widocznej utraty geometrii trasy. Wyłącz, jeśli potrzebujesz pełnego próbkowania przy prędkości (np. telemetria rajdowa).

## Informacje

**Ustawienia → Informacje** pokazuje wersję, atrybucje i e-mail kontaktowy — dodatkowo **Podręcznik użytkownika**: dotykalne wpisy dla każdego rozdziału tej dokumentacji, dostarczone w aplikacji, aby cały przewodnik działał offline. Dotknij rozdziału → otwiera się czytnik i renderuje rozdział w aplikacji. Linki między rozdziałami są honorowane; strzałka wstecz wraca do listy. Link **„Czytaj online”** u dołu otwiera tę samą dokumentację na [apexgps.duttra.de/docs](https://apexgps.duttra.de/docs/) w przeglądarce. Po pomoc: [sandwalker.one@proton.me](mailto:sandwalker.one@proton.me).

Pod Podręcznikiem użytkownika wiersz **Polityka prywatności** otwiera ten sam czytnik w aplikacji na rozdziale polityki prywatności — bez internetu możesz przeczytać, jakie dane aplikacja zbiera (żadne poza tym, co masz w telefonie) i jak są wykorzystywane. Ta sama treść jest zwierciadlana pod [apexgps.duttra.de/privacy.html](https://apexgps.duttra.de/privacy.html) dla każdego, kto chce ją przeczytać przed instalacją.

---

**Powiązane:** [FAQ →](faq.md) · [Kopia zapasowa →](backup.md)
