# Historia zmian

Zmiany widoczne dla użytkownika, najnowsze u góry. Refaktory wewnętrzne / podbicia wersji są w prywatnym repo.

---

## 1.35.2 — May 15, 2026 — Niezawodny kosz · Ikona kosza pojawia się tylko podczas przeciągania · Dotknięcie blisko punktów środkowych działa

- **Ikona kosza pojawia się teraz tylko podczas przeciągania — pojawia się w chwili, gdy przytrzymasz wierzchołek lub punkt środkowy, świeci się na czerwono po najechaniu i znika po puszczeniu.** Wcześniej ikona była zawsze widoczna w trybie pomiaru i planowania, ale gest „przytrzymaj-i-przeciągnij-na-kosz-żeby-usunąć" nie był oczywisty dla większości użytkowników — widzieli kosz, ale nie wiedzieli, jak doprowadzić do niego punkt. Teraz kosz pojawia się dopiero, gdy faktycznie chwycisz punkt, co czyni gest jasnym.
- **Upuszczenie punktu środkowego na koszu znów niezawodnie go usuwa.** Naprawiono dwa sporadyczne błędy: (1) drganie pozycji w chwili puszczenia palca czasem zostawiało współrzędne upuszczenia kilka pikseli poza strefą kosza, nawet gdy ikona świeciła się na czerwono — teraz sygnałem jest sam czerwony blask, więc jeśli widzisz czerwień w chwili puszczenia, punkt zostaje usunięty; (2) w kilku przypadkach punkt środkowy upuszczony na kosz zostawał wizualnie zaparkowany przy ikonie aż do następnej zmiany listy — teraz linia czysto wraca do pierwotnego kształtu przy każdym przerwaniu.
- **Dotknięcie linii blisko kropki punktu środkowego nie zniekształca już istniejącego odcinka.** Wcześniej, jeśli próbowałeś dotknąć linii, aby dodać nowy wierzchołek, ale trafiłeś blisko kropki punktu środkowego między dwoma istniejącymi wierzchołkami, istniejący odcinek się zniekształcał — Twoje dotknięcie zostawało przejęte jako niemal-zerowe przeciągnięcie, które wstawiało wierzchołek dokładnie w punkcie środkowym. Teraz dotknięcie jest rozpoznawane jako dotknięcie i nowy wierzchołek jest dodawany na końcu listy, dokładnie tak samo jak przy dotknięciu w dowolnym innym miejscu mapy.

---

## 1.35.1 — 15 maja 2026 — Poprawki kosza · Planowanie trasy zaczyna się tam, gdzie dotkniesz

- **Strefa-kosz znów działa, gdy mapa jest obrócona.** Wcześniej przeciągnięcie punktu pomiaru lub punktu planowania na ikonę kosza w prawym górnym rogu po cichu zawodziło, jeśli mapa była choć trochę obrócona — ikona nie świeciła się na czerwono, a upuszczenie nie usuwało punktu. Test kolizji odczytuje teraz surowe współrzędne palca zamiast wewnętrznej ramki obróconej mapy, więc kosz działa przy dowolnej orientacji.
- **Usunięcie pierwszego punktu pomiaru przy włączonym śledzeniu nie niszczy już kolejnego punktu.** Gdy mierzysz dystans z włączonym śledzeniem, pierwszy punkt (punkt A) sam podąża za Twoją bieżącą pozycją. Wyrzucenie go na kosz wcześniej zawodziło w mylący sposób: A wracał przy następnym fixu GPS, a punkt, który postawiłeś tuż po nim (B), po cichu znikał. Teraz wyrzucenie A trzyma A z dala do końca sesji pomiaru, a B i każdy kolejny punkt pozostają na miejscu. Wyłącz i włącz ponownie tryb pomiaru, aby na nowo zasiać A w Twojej bieżącej pozycji.
- **Planowanie trasy nie umieszcza już automatycznie punktu 1 w Twojej bieżącej pozycji.** Planowanie to świadomy proces na konkretnym obszarze mapy — większość użytkowników najpierw przesuwa mapę w okolicę, którą chce zaplanować, a dopiero potem wchodzi w tryb planowania. Auto-zasianie punktu 1 w pozycji GPS zaskakiwało użytkowników planujących odległe trasy. Planowanie startuje teraz pusto; pierwsze dotknięcie umieszcza punkt 1 dokładnie tam, gdzie dotknąłeś, gdziekolwiek przesunąłeś mapę.

---

## 1.35.0 — 14 maja 2026 — Udostępnij widoczne trasy i punkty · Oszczędzanie baterii przy dużej prędkości · GPX z komunikatorów

- **Udostępnij wszystko, co widać na mapie, jednym stuknięciem.** Nowa **ikona udostępniania** znajduje się w lewym górnym rogu mapy, tuż obok menu ☰. Stuknij ją, a otworzy się arkusz z listą każdej widocznej trasy + punktu w bieżącym kadrze. Zaznacz, co chcesz, stuknij **Udostępnij**, wybierz WhatsApp / e-mail / Drive — cała paczka wychodzi jako pojedynczy plik `.gpx` nazwany od obszaru, który oglądałeś (np. `ApexGPS-Wadi-Bani-Khalid-2026-05-14.gpx`). Dwa kolejne punkty wejścia korzystają z tego samego arkusza: karta **Udostępnij widoczne trasy i punkty** w menu Mapy (używa kadru, który miałeś otwarty w chwili otwarcia menu), oraz ikona **udostępniania** w górnym pasku list Trasy / Punkty, gdy długo przytrzymasz, aby zaznaczyć wiele elementów — pakuje zaznaczone elementy bezpośrednio bez dodatkowego arkusza.
- **Oszczędzanie baterii przy dużej prędkości.** Nowy przełącznik w **Ustawienia → Zaawansowane** (domyślnie włączony) zmniejsza próbkowanie GPS z raz na sekundę do raz na 10 sekund, gdy poruszasz się szybciej niż 36 km/h — samochód, pociąg, szybki rower elektryczny. Trasy drogowe są nadal rejestrowane czysto; dokładność pasa ruchu jest zmniejszona podczas jazdy. Tnie z grubsza połowę zużycia baterii GPS na autostradowym odcinku podróży bez widocznej utraty kształtu trasy. Wyłącz, jeśli potrzebujesz pełnego próbkowania przy prędkości.
- **Otwórz pliki `.gpx` jednym stuknięciem z WhatsApp / Telegram / Signal / Outlook.** Wcześniej załączniki z tych aplikacji spadały do systemowej przeglądarki tekstu, ponieważ ogłaszają plik jako generyczny `application/xml` zamiast kanonicznego typu MIME GPX. ApexGPS akceptuje teraz również te generyczne typy — stuknij raz załącznik `.gpx` w dowolnym komunikatorze, a systemowe menu „Otwórz w" pokaże ApexGPS jako opcję pierwszej klasy.
- **Kopie zapasowe map offline w trybie przepisu (między platformami).** Ustawienia → Dane → Kopia zapasowa zastępują jedno pole „Zapisane regiony map" trójstopniowym selektorem: **Nie dołączaj** / **Przepis** (mały — wymienia, które regiony pobrać ponownie, działa między Androidem a iOS) / **Pełne kafelki** (stare zachowanie — osadza surowe paczki kafelków, duży, ale można przywrócić offline, tylko Android). Kopia w trybie przepisu zajmuje około 80 KB nawet dla kilkunastu regionów; przywrócenie dodaje wiersze zastępcze w **Mapy → Zapisane mapy offline** z przyciskiem **Pobierz**, aby pobrać właściwe kafelki na żądanie.
- **Płatny styl mapy ukrywa się bez klucza.** Pozycja **Outdoors (Thunderforest)** znika teraz zarówno z selektora stylu mapy, jak i z selektora pobierania regionu offline, dopóki nie wkleisz klucza API w **Ustawienia → Klucze API**. Wcześniej wybranie jej bez klucza po cichu przełączało na OpenTopoMap bez wyjaśnienia. Wklej klucz → pozycja wraca w obu menu.

---

## 1.34.2 — 14 maja 2026 — Ukrywanie płatnych źródeł kafelków bez klucza

- **Styl „Outdoors (Thunderforest)" całkowicie się teraz ukrywa, dopóki nie wkleisz klucza API.** Wcześniej wybranie go bez klucza po cichu przełączało na OpenTopoMap bez żadnego wyjaśnienia — stukałeś Outdoors, widziałeś kafelki OpenTopoMap i nie wiedziałeś, dlaczego. Selektor stylu mapy oraz selektor pobierania regionu offline pomijają teraz pozycję Outdoors, dopóki **Ustawienia → Klucze API → Thunderforest** nie zawiera zapisanego klucza. Wklej klucz → Outdoors natychmiast wraca w obu menu.

---

## 1.34.1 — 13 maja 2026 — Format kopii v2 (przepisy regionów offline, między platformami)

- **Kopie zapasowe mogą teraz pomijać ciężkie paczki kafelków i zapisać zamiast nich „przepis".** Ustawienia → Dane → Kopia zapasowa zastępują jedno pole „Zapisane regiony map" trójstopniowym selektorem: **Nie dołączaj** / **Przepis** (mały — wymienia, które regiony pobrać ponownie, działa między Androidem a iOS) / **Pełne kafelki** (duży — stare zachowanie, tylko Android). Kopia w trybie przepisu zajmuje około 80 KB nawet dla kilkunastu regionów; odpowiadająca jej kopia z pełnymi kafelkami zajmowałaby 50–500 MB. Po przywróceniu kopii w trybie przepisu lista zapisanych map wypełnia się wierszami oznaczonymi „Jeszcze nie pobrano · X kafelków" z przyciskiem **Pobierz** — stuknij, aby pobrać ponownie z oryginalnego serwera kafelków (używa Twojej obecnej pamięci podręcznej + świeżego pobrania reszty).
- **Kopia utworzona na Androidzie może teraz zostać przywrócona na iOS i odwrotnie — wszystko poza paczkami z pełnymi kafelkami.** Trasy, punkty, ustawienia i przepisy regionów krążą czysto między platformami. Tryb pełnych kafelków pozostaje tylko dla Androida, bo iOS nie ma konsumenta MBTiles, ale tryb przepisu pokrywa praktyczne potrzeby większości użytkowników (odbudowa na nowym telefonie, akceptacja krótkiego pobrania regionów, na których Ci zależy).
- **Przywracanie przepisu w stylu Outdoors przypomina najpierw o ustawieniu klucza API.** Jeśli przywrócony przepis celuje w Thunderforest, a nie masz zapisanego klucza, stuknięcie **Pobierz** pokazuje jednorazowy komunikat kierujący do **Ustawienia → Zaawansowane → Klucz API Thunderforest**; gdy klucz jest na miejscu, pobieranie rusza normalnie.

---

## 1.34.0 — 13 maja 2026 — Dopasowanie rozmiarów · Sporty wodne · Postęp przywracania na żywo · Poprawne formy mnogie

- **Znaczniki punktów trasy są domyślnie około 25 % większe.** „Normalny" (1,0×) renderuje się teraz w rozmiarze, który wcześniej miał „Duży". Jeśli znaczniki wydają się za małe, selektor nadal oferuje Mały / Normalny / Duży / XL — Ustawienia → Wygląd → Rozmiar znacznika. Twoje obecne ustawienie zostaje zachowane; rozważ obniżenie o jeden stopień, ponieważ cała skala urosła.
- **Suwaki przycinania — okrągłe uchwyty działają z dowolnego miejsca.** Wcześniej reagowała tylko pionowa linia każdego uchwytu; dotknięcie okrągłego przycisku na dole często nic nie robiło, bo strefa dotyku nie sięgała do samego dołu. Naprawione — oba okrągłe uchwyty można teraz chwycić z dowolnego miejsca na kółku plus małego pasa pod nim.
- **Nowy typ aktywności: Sporty wodne.** Wybierz w Szczegóły trasy → Aktywność, aby oznaczyć sesję kajakową, żeglarską, surfingową lub inny sport wodny. Ta sama ikona fali co znacznik wodospadu.
- **Przywracanie kopii zapasowej pokazuje teraz postęp na żywo.** Duża kopia (setki tras, tysiące punktów) wcześniej blokowała aplikację na wskaźniku obracającym się przez kilka minut bez sygnału postępu — łatwo pomylić z awarią. Przycisk Przywróć siedzi teraz nad paskiem postępu + opisem („Przywracanie trasy N z M…" / „Przywracanie punktu N z M…"), który tyka co trasę i co 100 punktów.
- **Polski i arabski pokazują teraz poprawnie odmienione etykiety z liczbami.** 13 ciągów z licznikami („X tras", „Y punktów", „Z minut temu" itd.) przechodzi teraz przez prawdziwe reguły liczby mnogiej. Polski otrzymuje wszystkie 4 formy (1 trasa / 2 trasy / 5 tras / 1,5 trasy); arabski wszystkie 6. Angielski / niemiecki / francuski / hiszpański były już gramatycznie poprawne; spójna obsługa w jednej ścieżce.

---

## 1.33.8 — 10 maja 2026 — Kolejka pierwszego punktu pomiaru i planera

- **Stuknięcie narzędzia pomiaru lub FAB-a planera trasy przed nadejściem fixu GPS automatycznie upuszcza pierwszy punkt, gdy tylko pozycja się pojawi.** Wcześniej stuknięcie w trakcie rozgrzewki GPS zostawiało puste rozpoczęcie — trzeba było ręcznie stuknąć mapę, żeby upuścić punkt A. Aplikacja pokazuje teraz „Szukam GPS…" na przełączniku i zakolejkowuje auto-upuszczenie pierwszego punktu; gdy pojawi się fix, punkt A pojawia się w Twojej pozycji, a śledzenie na żywo przejmuje normalnie. Działa tak samo jak FAB nagrywania od 1.33.7. Ręczne stuknięcie mapy w międzyczasie anuluje kolejkę, więc żadne stuknięcie nie ginie.

---

## 1.33.7 — 10 maja 2026 — Tolerancyjny import GPX · Prywatność w Informacjach · Auto-start nagrywania

- **Importy plików GPX z błędnymi współrzędnymi nie przerywają już całego importu.** Punkt trasy lub waypoint z błędną wartością `lat` / `lon` przerywał wcześniej cały import. Aplikacja pomija teraz zły punkt i kontynuuje importowanie reszty — jeden błędny punkt w 10 000-punktowej wędrówce nie powoduje już utraty pliku. Twarde górne limity (10 tys. tras, 100 tys. punktów, 500 tys. punktów na trasę) nadal wyrzucają wyjątek, aby zapobiec wyczerpaniu pamięci.
- **Polityka prywatności bezpośrednio pod Ustawienia → Informacje.** Nowy wiersz „Polityka prywatności" znajduje się pod Podręcznikiem użytkownika; stuknij, aby przeczytać politykę w aplikacji, bez internetu. Ta sama treść jest zwierciadlana pod [apexgps.duttra.de/privacy.html](https://apexgps.duttra.de/privacy.html) (adres URL polityki prywatności w Play Store) dla każdego, kto chce ją przeczytać przed instalacją.
- **Stuknij Nagrywaj przed pierwszym fixem GPS i nagrywanie auto-startuje po jego nadejściu.** Wcześniej stuknięcie Nagrywaj przed otrzymaniem jakiegokolwiek fixu natychmiast rozpoczynało pustą trasę okruchów — jeśli stuknąłeś Stop przed nadejściem fixu, zapisywałeś trasę z zerową liczbą punktów. Teraz komunikat mówi „Szukam GPS…", a nagrywanie automatycznie startuje w chwili pojawienia się pierwszego fixu — żadne drugie stuknięcie nie jest potrzebne.

---

## 1.33.6 — 9 maja 2026 — Niezawodna strefa-kosz po powrocie z ostatnich aplikacji

- **Strefa-kosz służąca do usuwania punktów podczas planowania trasy i pomiaru znów działa niezawodnie po zminimalizowaniu aplikacji i ponownym otwarciu z listy ostatnich aplikacji.** Ukryta usterka powodowała, że gest "przeciągnij punkt na kosz, aby go usunąć" po cichu przestawał działać po odłączeniu i ponownym podłączeniu okna aplikacji (minimalizacja → dotknięcie z ostatnich aplikacji). Granice strefy-kosza pozostawały na współrzędnych sprzed minimalizacji, podczas gdy pozycja mapy nadal się aktualizowała, więc upuszczanie nie było już wykrywane. Test kolizji odczytuje teraz granice na świeżo przy każdym zdarzeniu przeciągania (i tylko wtedy, gdy ikona kosza jest faktycznie podłączona do okna) — dzięki czemu strefa-kosz działa poprawnie po dowolnej liczbie cykli powrotu. Restart aplikacji jako obejście nie jest już potrzebny.
- **Wewnętrzne: porządki w buildzie pod weryfikację produkcyjną Play Store.** Aktualizacja zależności UI (`androidx.activity:activity-compose` 1.9.3 → 1.10.1) rozwiązująca ostrzeżenia Vitals zgłoszone w weryfikacji 1.33.5 ("edge-to-edge może nie wyświetlać się wszystkim użytkownikom") — czyste porządki, bez zmian w zachowaniu. Włączono ekstrakcję natywnych symboli debugowania dla buildów release (dziś bez efektu, bo jedyne biblioteki natywne w AAB są dostarczane bez symboli przez Google — uruchomi się automatycznie, jeśli przyszła zależność dostarczy symbole).

---

## 1.33.5 — 7 maja 2026 — Konfigurowalny rozmiar cache\'u kafli + powitalna trasa po świeżej instalacji

- **Wybierz, ile miejsca na dysku przeznaczyć na cache kafli.** Ustawienia → Cache offline mają teraz cztery wartości do wyboru: 250 MB / 500 MB (domyślny) / 1 GB / 2 GB. Nowy limit zaczyna działać natychmiast — restart nie jest potrzebny. Zapisane regiony offline są przechowywane osobno i nie wliczają się tutaj, więc zmiana tej wartości nigdy nie usuwa regionu, który świadomie pobrałeś.
- **Powitalna trasa przy każdej nowej instalacji.** Prawdziwy zapis **trawersowania Watzmanna** (Berchtesgaden, Niemcy) — Wimbachbrücke → Watzmannhaus → Hocheck → Mittelspitze → Südspitze → Wimbachgrieshütte → Wimbachbrücke, pętla ~22,6 km / +2250 m / około 10–12 h marszu — jest automatycznie importowany przy pierwszym uruchomieniu aplikacji. Wraz z trasą pojawiają się trzy punkty orientacyjne (początek Wimbachbrücke, DAV Watzmannhaus, Watzmann-Mittelspitze). Istniejące instalacje nie są dotykane. Jeśli usuniesz przykłady i będziesz chciał je z powrotem, **Ustawienia → Dane → Wczytaj dane przykładowe** sprowadzi je z powrotem na żądanie.

---

## 1.33.4 — 5 maja 2026 — Porządki w uprawnieniach na karcie w Sklepie Play

- **Czystsza lista uprawnień w Sklepie Play.** Usunięto przestarzałą deklarację „pamięci USB", która nie była nigdy używana — aplikacja buforuje kafle we własnej pamięci wewnętrznej, nie na USB / pamięci współdzielonej. Strona uprawnień pokazuje teraz cztery wpisy mniej; w samym telefonie nic się nie zmienia.

---

## 1.32.2 — 26 kwi 2026 — Pogoda domyślnie włączona + pełne tłumaczenia + przycisk Wstecz w Mapach

- **Pogoda jest teraz domyślnie włączona.** Chip prognozy i wiersz „Pogoda tutaj" przy punktach są widoczne bez konieczności wcześniejszego włączenia ustawienia. Możesz nadal wyłączyć pogodę w **Ustawienia → Pogoda**, jeśli wolisz brak połączeń sieciowych — istniejące instalacje zachowują Twoje wcześniejsze ustawienie.
- **Pełne tłumaczenia funkcji pogody.** Wszystkie teksty pogodowe — chip, arkusz (panel bieżący, pasek 24-godzinny, trendy wilgotności / ciśnienia, pasek 7-dniowy, etykiety zachodu / UV / ciśnienia / punktu rosy), wiersze w Ustawieniach i tytuł rozdziału przewodnika — są teraz przetłumaczone na niemiecki, francuski, hiszpański, polski i arabski. Warunki pogodowe („Lekki deszcz", „Burza z gradem", „Częściowe zachmurzenie", …) używają standardowego słownictwa meteorologicznego w każdym języku.
- **Menu Mapy: przycisk Wstecz najpierw zamyka otwartą kartę.** Gdy **Pobierz nowy obszar** lub **Zapisane mapy offline** były rozwinięte, Wstecz pomijał menu Mapy i przenosił Cię z powrotem na główną mapę. Teraz Wstecz najpierw zamyka otwartą kartę; kolejne naciśnięcie wraca do głównej mapy. To pokrywa się z zachowaniem w innych miejscach (podekrany Ustawień, wielokrotny wybór na listach tras / punktów).

---

## 1.32.1 — 25 kwi 2026 — Pogoda: drobne poprawki

- **Poprawne ikony słońca / księżyca po północy.** 24-godzinny pasek pogody pokazywał glify księżyca dla popołudniowych godzin *następnego* dnia (11:00, 14:00, 17:00), gdy arkusz otwierano późno wieczorem. Każda godzina wybiera teraz własny wschód / zachód słońca, więc godziny dzienne zawsze pokazują ikony strony słońca.
- **Prognoza waypointa rzeczywiście używa jego wysokości.** Gdy waypoint na szczycie znajdował się praktycznie w tych samych współrzędnych co Twoje aktualne odczyty GPS, czasem zwracana była buforowana prognoza dla bieżącej pozycji zamiast świeżego zapytania uwzględniającego wysokość. Na szczycie 1480 m prognoza była ~9 °C za ciepła. Cache uwzględnia teraz także wysokość jako klucz, więc zapisana wysokość waypointa jest zawsze respektowana.

---

## 1.32.0 — 25 kwi 2026 — Pogoda: dopracowanie punktowe, bez nakładek na mapie

Po 1.31.0 siatkowe nakładki pogody nie przeszły testu wzrokowego na poziomach zoomu odpowiednich dla wędrówek — wyglądały jak blokowe kolorowe kwadraty bez prawdziwego dopasowania do terenu, a dolny rząd kontrolek (suwak nakładki + chip + pasek prędkość / wysokość / dystans) zjadał za dużo ekranu. Ta wersja czyści mapę i stawia na arkusz punktowy, gdzie są naprawdę przydatne szczegóły.

- **Nakładki na mapie usunięte.** Bez radaru opadów ani warstwy zachmurzenia na mapie podstawowej, bez suwaka czasu. Ekran **Ustawienia → Pogoda** zmniejsza się do jednego głównego przełącznika.
- **Bogatszy arkusz punktowy.** Arkusz pogody (stuknij chip lub wiersz „Pogoda tutaj" przy waypoincie) pokazuje teraz: panel bieżący z emoji pogody, temperaturą, „odczuwalna"; wiersze na wiatr / wilgotność / punkt rosy / ciśnienie / UV / zachód; pasek 24 godzin z godzinowymi ikonami pogody + temperaturą; trend wilgotności (jasnoniebieski) i trend ciśnienia (zielony); pasek 7 dni z maks / min + ikoną. Zaprojektowany, by zmieścił się na typowym ekranie telefonu.
- **Wysokość waypointa trafia do prognozy.** Waypointy z zapisaną wysokością przekazują ją do modelu, więc prognozy szczytów używają prawdziwej wysokości zamiast uśrednionej grubo przez model. To samo dla chipa pozycji bieżącej — używa Twojej wysokości GPS.
- **Chip dopasowany do karty waypointa.** Tekst chipa w pasku statystyk odpowiada teraz temu, co widzisz po stuknięciu waypointa: emoji + temp + wiatr. Pomiędzy chipem a wierszem prędkość / wysokość / dystans dodano cienki separator, żeby czytały się jako jeden panel.

---

## 1.31.0 — 25 kwi 2026 — Pogoda

ApexGPS pokazuje teraz informacje pogodowe poziomu wędrówkowego z darmowych publicznych API, w pełni opt-in.

- **Chip prognozy w pasku statystyk.** Po włączeniu pogody w **Ustawienia → Pogoda** mały chip nad paskiem prędkość / wysokość / dystans pokazuje aktualne warunki dla pozycji GPS: temperaturę, wiatr, wilgotność. Chip aktualizuje się co 15 minut online i sygnalizuje, gdy dane są stare lub jesteś offline (szarzeje + dodaje zegar).
- **Rozwijany arkusz.** Stuknij chip (lub nowy wiersz „Pogoda tutaj" w panelu waypointa) po pełny rozkład — bieżące odczyty, kolejne 24 godziny jako linia temperatury + słupki opadów oraz pasek 7 dni z maks/min i ikonami.
- **Ręczne odświeżenie.** Przycisk ↻ w nagłówku arkusza wymusza świeże zapytanie po ponownym połączeniu.
- **Animowane nakładki na mapie.** Nowa sekcja **Nakładki** w hubie Mapy dodaje dwa niezależne przełączniki: radar opadów (animowany kolorowy deszcz, ostatnie 2 h + 30-minutowy nowcast) i satelita chmur (geostacjonarny IR). Nie wysyłają Twojej pozycji nigdzie — to czyste pobrania kafli, niezależne od chipa pogody.
- **Prywatność na pierwszym miejscu.** Cała funkcja jest domyślnie wyłączona. Prognozy z Open-Meteo, radar z RainViewer; obie publiczne darmowe API bez konta i bez klucza. Twoja pozycja jest wysyłana tylko, gdy wyraźnie włączysz chip.

Przeczytaj pełny rozdział w **Ustawienia → Podręcznik → Pogoda**.

---

## 1.30.2 — 25 kwi 2026

- **Stuknięcie kompasu respektuje blokadę rotacji.** Długie naciśnięcie kompasu blokuje rotację mapy; gdy zablokowana, pojedyncze stuknięcie kompasu nie przyciąga już mapy do północy. (Trzeba ponownie długo nacisnąć, by odblokować, dopiero potem stuknąć.) Przywraca to intencję blokady — zamrożenie kąta przed przypadkowymi wejściami, w tym błędnym stuknięciem samego kompasu.
- **Krótsze, mniej natrętne komunikaty.** Komunikaty „Usunięto …" / „Przeniesiono …" / „Dotarcie" / podążanie-zablokowane / auto-pauza-lokalizacja-wyłączona pokazują się teraz jako krótki Toast Androida (~2 s, system overlay) zamiast 4-sekundowego snackbara, który blokował dół mapy. Możesz stuknąć inny waypoint zaraz po usunięciu jednego, bez czekania.

---

## 1.30.0 / 1.30.1 — 25 kwi 2026 — Jakość nagrywania

Pierwszy hike po 1.29 (4 h 10 min, 9,98 km) ujawnił, że nagrywanie live tracku zapisywało dużo więcej punktów niż potrzeba i wchłonęło duży fałszywy spadek wysokości spowodowany utkniętą wartością wysokości. Oba naprawione:

- **Lżejsze, gładsze nagrania.** Nowy filtr zachowuje fix tylko, jeśli ruszyłeś się co najmniej 5 m, minęło 15 sekund albo wysokość zmieniła się o 3 m+. Mocno nieprecyzyjne fixy (>25 m) są odrzucane od razu. Na hike testowym: ~4600 → ~1500 zapisanych punktów, brak widocznej zmiany linii trasy, dystans bez zmian. Mniej miejsca; mniejsze eksporty GPX; ten sam ślad.
- **Koniec z fałszywymi załamaniami wysokości.** Fused location provider niektórych Androidów zacina się i zwraca tę samą buforowaną wysokość (np. `139 m` na hike na 1200 m) przez minuty. Nagrywanie traktuje teraz takie odczyty jako „brak wartości" zamiast utrwalać błędną liczbę. Profil wysokości pokazuje czystą lukę zamiast zjazdu do zera, a statystyki wzniesienia / spadku odzwierciedlają tylko prawdziwe zmiany.
- **Wysokość MSL na Androidzie 14+.** Tam, gdzie jest dostępna, nagrywanie używa uczciwszej wysokości względem średniego poziomu morza zamiast fallbacku WGS84 podatnego na powyższe zacinanie.

Jeśli masz nagranie sprzed 1.30.0 z błędnym odczytem wysokości, możesz je powtórzyć — wyświetlanie tracku w aplikacji używa zapisanych punktów. Brak kroku migracji.

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
