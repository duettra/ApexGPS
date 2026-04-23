# Mapy offline

ApexGPS działa bez sygnału, jeśli kafelki mapy dla obszaru są już w telefonie. Dwa sposoby: automatyczne zapisywanie i ręczne pobieranie wstępne.

## Automatyczne zapisywanie

Wszystko, na co patrzyłeś mając sygnał, trafia do pamięci podręcznej kafelków. Powrót do tego obszaru offline → kafelki ładują się natychmiast z pamięci.

Pamięć jest **dla każdego źródła oddzielnie** — OpenTopoMap i Satelita to osobne magazyny. Przeglądanie obszaru w OpenTopoMap nie pomoże, jeśli offline przełączysz na Satelitę.

Rozmiar pamięci pokazuje **Ustawienia → Pamięć** z podziałem na źródła.

## Ręczne pobieranie wstępne (zalecane przed wyjazdem)

Przed wyruszeniem tam, gdzie nie ma zasięgu, pobierz region świadomie:

### Wybierz obszar

1. Przesuń/powiększ mapę tak, aby interesujący obszar wypełnił ekran.
2. **Menu → Mapy** → dotknij **Pobierz nowy obszar**.
3. Mała mapa podglądu pokazuje bieżący obszar. Dostosuj w razie potrzeby.

### Ustaw zakres zoomu

**Suwak** określa zapisywane poziomy. Większy zoom = więcej szczegółów, ale wykładniczo więcej kafelków.

- Na **weekendową wycieczkę**: 10–16 zwykle wystarcza.
- Na **dłuższą wyprawę** / tydzień: 10–17 lub 10–18 dla maksimum detali.
- Zoom 19+ rzadko się opłaca w terenie — dużo kafelków, mało dodatkowej informacji.

Interfejs pokazuje szacunkową **liczbę kafelków** i **rozmiar MB** w trakcie przesuwania suwaka. Porównaj z wolnym miejscem.

### Pobierz

Dotknij **Pobierz**. Pojawia się powiadomienie pierwszego planu; możesz wyjść z aplikacji, zablokować telefon — pobieranie kontynuuje. Postęp w powiadomieniu i w hubie Mapy.

Aby anulować w trakcie: hub Mapy → karta pobierania ma przycisk **Anuluj**. (Naciśnięcie wstecz NIE anuluje — celowo, abyś mógł przeglądać trasy, gdy kafelki się pobierają.)

### Tylko aktywne źródło

Pobieranie używa źródła aktywnego przy starcie. Aby zapisać inny styl, najpierw zmień źródło (FAB warstw), potem uruchom.

## Zapisane regiony (menu → Mapy → Zapisane mapy offline)

Każde ukończone pobieranie pojawia się tutaj. Dotknij regionu, aby otworzyć szczegóły:

- **Nazwa** — edytowalna. Domyślnie na podstawie kraju/regionu zgeokodowanego z ramki.
- **Źródło**, **zakres zoomu**, **liczba kafelków**, **rozmiar na dysku**.
- **Pokaż na mapie** — zamyka szczegóły i dopasowuje zoom do ramki.
- **Usuń** — zwalnia miejsce. Z potwierdzeniem.

Usunięcie zapisanego regionu usuwa jego paczkę kafelków, ale NIE wpływa na ogólną pamięć. Obszar może być nadal zapisany z wcześniejszego przeglądania.

## Zarządzanie pamięcią (menu → Ustawienia → Pamięć)

- **Łączny rozmiar pamięci** wszystkich źródeł.
- **Podział wg źródła** — ile MB zajmuje każdy styl.
- **Wyczyść wszystko** — usuwa kafelki przeglądania dla każdego stylu. NIE usuwa zapisanych regionów (osobne pliki).
- **Wyczyść [źródło]** — tylko dla danego stylu.

Zapisane regiony offline są zarządzane w hubie Mapy, nie tutaj.

## Co korzysta z sieci na szlaku

Nawet ze wszystkim w pamięci, kilka rzeczy może próbować sieci:

- **Zmiana stylu** jeśli nowy nie jest zapisany dla obszaru — kafelki zostaną puste.
- **Thunderforest (Outdoors)** — kafelki przez HTTPS z Twoim kluczem API.
- Nic więcej. Trasy, punkty i nawigacja są w pełni lokalne.

Gdy telefon nie ma zasięgu, na górze pojawia się **Offline**. To sygnał urządzenia, nie wybór aplikacji.

## Wskazówki

- **Zawsze pobieraj przed wyjazdem.** Nie polegaj na automatycznej pamięci — obejmuje tylko to, na co faktycznie patrzyłeś.
- **Dwa style** mogą pomóc: OpenTopoMap dla poziomic + ścieżek, Satelita dla realnego wyglądu. Pobierz oba dla kluczowych obszarów.
- **Wyższy zoom = więcej miejsca, malejące korzyści.** Powyżej zoomu 17 dodatkowe szczegóły rzadko pomagają w znajdowaniu drogi; to głównie kształty budynków i etykiety ulic.
- **Sprawdź wolne miejsce przed dużym pobieraniem.** Duży region w zoomie 18 może łatwo przekroczyć 500 MB.

---

**Powiązane:** [Ekran mapy →](map.md) · [Ustawienia →](settings.md) · [Kopia zapasowa →](backup.md)
