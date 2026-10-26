# Paura

**Paura (Paczka + Faktura)** to lokalna aplikacja dla systemu Windows, wspomagająca codzienną obsługę sprzedaży na platformie Allegro.

Aplikacja jest przeznaczona do prywatnego użytku w dwóch niezależnych sklepach. Nie jest usługą SaaS ani publicznie udostępnianym systemem dla sprzedawców.

## Funkcjonalności

- **Zamówienia Allegro:** synchronizacja zamówień, podgląd szczegółów i statusów oraz zarządzanie wysyłką.
- **Wysyłam z Allegro:** tworzenie przesyłek dla obsługiwanych metod dostawy, zbiorcze nadawanie i generowanie etykiet A6/A4.
- **Faktury VAT:** automatyczne przygotowywanie szkiców na podstawie opłaconych zamówień z żądaniem faktury, ręczne wystawianie i obsługa faktur korygujących.
- **KSeF 2.0:** integracja z Krajowym Systemem e-Faktur, obsługa FA(3), statusów dokumentów i UPO.
- **Dokumenty Allegro:** przekazywanie plików PDF faktur do odpowiednich zamówień.
- **Historia:** lokalna ewidencja dokumentów, przesyłek i operacji.

## Architektura i bezpieczeństwo

Paura działa lokalnie na komputerze użytkownika, z wykorzystaniem interfejsu dostępnego w przeglądarce.

Dane poszczególnych sklepów są przechowywane w oddzielnych lokalnych instalacjach. Aplikacja komunikuje się z Allegro za pomocą oficjalnego REST API i OAuth, a z KSeF za pomocą oficjalnego API KSeF 2.0.

Dostęp do konta Allegro wymaga autoryzacji przez jego właściciela. Aplikacja nie wymaga przekazywania hasła Allegro.

## Status projektu

Aplikacja jest w fazie przygotowania do wdrożenia produkcyjnego. Funkcje Allegro i KSeF były rozwijane oraz testowane w środowiskach Allegro Sandbox i KSeF TEST.

Uruchomienie produkcyjne oraz niezależne instalacje Windows są przygotowywane.

## Kontakt

W sprawach technicznych: bloomnote.studio@gmail.com

---

*Paura jest niezależnym projektem i nie stanowi oficjalnej aplikacji Allegro ani Ministerstwa Finansów.*

Repozytorium ma charakter wyłącznie informacyjny. Nie zawiera kodu źródłowego aplikacji, danych klientów ani poufnych danych uwierzytelniających.
