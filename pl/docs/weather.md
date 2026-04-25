# Pogoda

ApexGPS może pokazać aktualne warunki, prognozę godzinową i 7-dniową dla dowolnego punktu, który Cię interesuje. Wszystko jest opt-in.

## Włączanie pogody

Otwórz **Ustawienia → Pogoda** i włącz **Pokaż pogodę**. Po włączeniu:

- Mały chip pojawia się nad paskiem statystyk i pokazuje warunki w Twojej aktualnej pozycji GPS.
- Stuknięcie waypointa pokazuje wiersz „Pogoda tutaj" w panelu waypointa.
- Stuknięcie któregokolwiek otwiera arkusz z pełnym rozkładem.

Domyślnie **wyłączone**, by aplikacja nie wysyłała Twojej pozycji do serwisu zewnętrznego bez Twojej zgody. Po włączeniu Twoja szerokość/długość jest wysyłana do Open-Meteo (darmowe publiczne API pogodowe) przy każdym zapytaniu.

## Co pokazuje chip

Chip rotuje pomiędzy kilkoma stanami:

| Stan | Wygląda jak | Znaczenie |
|---|---|---|
| Świeży | `☼ 24° · 12 km/h NE` | Aktualizacja w ciągu ostatnich 15 minut. |
| Starzejący się | `… · 32 min temu` | Ponad 15 minut, ale prawdopodobnie nadal trafny. |
| Przestarzały / offline | `⚠ … · 2h temu` (szary) | Ponad godzina lub brak połączenia. Stuknij chip, aby ręcznie odświeżyć. |

Chip nie znika, gdy pogoda jest włączona — zmienia tylko wygląd, by pokazać, jak wiarygodne są dane.

## Arkusz prognozy

Stuknij chip (lub wiersz „Pogoda tutaj" przy waypoincie), by otworzyć pełny arkusz. Z góry na dół:

- **Teraz** — duży emoji pogody + temperatura, „odczuwalna" oraz po jednym wierszu na wiatr / wilgotność + maks. opady / punkt rosy + UV / ciśnienie + zachód.
- **Następne 24 godziny** — osiem ikon co 3 godziny (strona słońca lub strona księżyca w zależności od lokalnego wschodu / zachodu dla danej godziny) z godzinową temperaturą.
- **Trend ciśnienia** (zielony) — wykres liniowy 24-godzinny, przydatny do wykrywania zbliżającego się frontu.
- **Trend wilgotności** (jasnoniebieski) — wykres liniowy 24-godzinny.
- **Następne 7 dni** — rząd ikon dni tygodnia z maksymalną / minimalną temperaturą.

W nagłówku arkusza jest przycisk odświeżania (↻), który pomija cache i pobiera świeże dane. Offline poprzednie dane pozostają na ekranie, a wskaźnik „przestarzałe" chipa pozostaje widoczny.

## Prognozy świadome wysokości na szczytach

Jeśli waypoint ma zapisaną wysokość (wpisaną ręcznie, ustawioną z GPS lub zaimportowaną z GPX z `<ele>`), ta wysokość jest wysyłana do Open-Meteo, by model wiedział, że to szczyt, a nie punkt doliny przy tych samych współrzędnych. To samo dla chipa: używa Twojej wysokości GPS. Na szczycie 1500 m zwykle koryguje to prognozowaną temperaturę o ~9 °C w porównaniu z zapytaniem tylko po współrzędnych.

## Auto-odświeżanie

Gdy pogoda jest włączona, chip aktualizuje się co 15 minut, dopóki aplikacja jest otwarta i online. W trybie samolotowym chip zachowuje ostatnie znane dane i wskaźnik „przestarzałe", aż połączysz się ponownie.

## Źródła danych

Prognozy pochodzą z **[Open-Meteo](https://open-meteo.com)**, darmowego publicznego API łączącego ECMWF, GFS, ICON i inne globalne modele najwyższej klasy. Darmowe dla użytku osobistego, bez konta, bez klucza API.

## Ograniczenia

- **Konwekcyjny deszcz w regionach suchych** jest trudny do prognozowania dla każdego modelu. Spodziewaj się okazjonalnych pomyłek przy nagłych burzach w miejscach takich jak góry Hajar w ZEA. Liczba prawdopodobieństwa jest co do tego szczera, ale lokalne zjawiska mogą wypaść poza siatkę.
- **Ostrzeżenia o zjawiskach groźnych** nie są częścią tej funkcji. ApexGPS nie wysyła powiadomień push przy zbliżających się burzach.
- **Pogoda wzdłuż trasy** nie jest wspierana — prognozy są punktowe, a nie „jaka będzie pogoda na tym szlaku za 2 godziny". Możesz stuknąć poszczególne waypointy wzdłuż trasy, by sprawdzać punktowo.
