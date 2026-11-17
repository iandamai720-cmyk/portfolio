# Wersja przeszła wszystkie testy automatyczne, ale nie działała dobrze na telefonie

[English](prewalk-release-acceptance.md) · [Prewalk](../projects/prewalk/README.pl.md)

**Projekt:** strona Prewalk · **Data:** 29 października 2026 · **Moja rola:** odbiór wersji na prawdziwym urządzeniu

## Sytuacja

Nowa wersja strony głównej Prewalk dodała animowany rzut 3D na górze strony. Przed publikacją przeszły budowanie strony, 35 testów automatycznych i 20 kontroli interfejsu, w tym testy pierwszego przewinięcia na emulowanym telefonie.

## Co zauważyłem

Na moim Pixelu 9, w kilku przeglądarkach, pierwsze przewinięcie strony się zacinało. Działo się tak również po odczekaniu 10 sekund na załadowanie strony, więc nie chodziło tylko o wolne łącze. Nie odebrałem tej wersji.

## Co było dalej

Agent AI przeanalizował działanie strony i znalazł jednorazową, ciężką pracę graficzną uruchamianą przy pierwszym dotknięciu. Testy na emulatorze jej nie mierzyły. Agent zmienił sposób ładowania sceny 3D i dodał testy regresji.

Sprawdziłem nową wersję na tym samym telefonie. Zacinanie wyraźnie się zmniejszyło, ale przez pierwsze 1 do 1,5 sekundy rzut nadal przeskakiwał. To również zgłosiłem, a kolejna poprawka została opublikowana tego samego dnia.

## Kto co zrobił

| Ja | Agent AI |
|---|---|
| Test na fizycznym telefonie i w kilku przeglądarkach | Analiza działania strony i znalezienie przyczyny |
| Opis objawu i tego, co już wykluczyłem | Zmiana kodu i dodanie testów |
| Odrzucenie wersji i sprawdzenie każdej poprawki | Dokumentacja każdej wersji |

## Wniosek

Zaliczone testy nie gwarantują dobrego działania na urządzeniu klienta. Przydatne zgłoszenie mówi, na jakim urządzeniu i w jakiej przeglądarce, kiedy występuje problem i co już wykluczono. Te same informacje przekazałbym programiście, pracując we wsparciu.
