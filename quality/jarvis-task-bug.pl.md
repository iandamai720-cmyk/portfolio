# Odpowiedź bez zapisanego zadania

[English](jarvis-task-bug.md) · [Jarvis](../projects/jarvis/README.pl.md)

**Projekt:** Jarvis · **Data:** listopad 2026 · **Moja rola:** zgłoszenie problemu i sprawdzenie poprawki

## Problem

Poprosiłem Jarvisa przez Telegram o dodanie zadania. Asystent odpowiedział, ale w Trello nie pojawiła się karta. Odpowiedź nie twierdziła, że karta została zapisana, lecz prośba nie została wykonana: potraktowano ją jak zwykłą rozmowę, a nie polecenie dodania zadania.

## Przykładowe kroki

Poniższa treść to neutralny przykład, a nie oryginalna wiadomość.

1. W Telegramie wysłać: „Dodaj do zadań na jutro przygotowanie demo”.
2. Na pytanie asystenta wybrać grupę zadań.
3. Porównać odpowiedź asystenta ze stanem tablicy Trello.

**Oczekiwane:** asystent dopytuje o brakujące informacje, tworzy jedną kartę we właściwej grupie i z właściwą datą oraz potwierdza, co zapisał. Jeżeli nie może zapisać karty, jasno o tym mówi.

**Faktyczne:** odpowiedź tekstowa i brak karty na tablicy.

## Poprawka i ponowne sprawdzenie

Zgłosiłem rozbieżność z przykładami z użycia. Agenty AI znalazły przyczynę, zmieniły obsługę takich próśb i dodały testy regresji. Po poprawce zapis potwierdza jedną kartę we właściwej grupie i z właściwą datą.

Osobno dodałem i zamknąłem testowe zadanie przez Telegram i przez telefon oraz sprawdziłem, że zamknięte zadanie nie pojawia się w kolejnym planie dnia.

## Wniosek

Gdy asystent lub integracja coś deklaruje, sprawdzam wynik w połączonym narzędziu. Odpowiedź, szkic i zapisane zadanie to trzy różne wyniki.
