# Paura

**Paura (Paczka + Faktura)** to lokalna aplikacja dla systemu Windows, wspomagająca codzienną obsługę sprzedaży na platformie Allegro.

Aplikacja umożliwia obsługę od **jednego do trzech kont sprzedawców Allegro** w ramach jednej instalacji, z zachowaniem niezależności zamówień, przesyłek i autoryzacji poszczególnych kont.

Projekt jest przeznaczony wyłącznie do prywatnego użytku w dwóch niezależnych firmach rodzinnych:

- **Pierwsza instalacja:** jedno konto sprzedawcy Allegro.
- **Druga instalacja:** trzy konta sprzedawców Allegro należące do tej samej firmy.

Łącznie aplikacja będzie obsługiwać cztery konta Allegro na dwóch niezależnych komputerach.

Paura nie jest usługą SaaS, nie jest publicznie udostępnianym systemem dla sprzedawców ani produktem oferowanym komercyjnie.

## Funkcjonalności

- **Zamówienia Allegro:** synchronizacja zamówień z podłączonych kont, podgląd szczegółów i statusów, wyszukiwanie, filtrowanie oraz zarządzanie wysyłką.
- **Wysyłam z Allegro:** tworzenie przesyłek dla obsługiwanych metod dostawy, zbiorcze nadawanie, pobieranie numerów przesyłek oraz generowanie i ponowne pobieranie etykiet A6/A4.
- **Faktury VAT:** automatyczne przygotowywanie szkiców na podstawie opłaconych zamówień z żądaniem faktury, ręczne wystawianie dokumentów oraz obsługa faktur korygujących.
- **Numeracja faktur:** automatyczna i ręczna numeracja, konfigurowalne wzory numerów oraz wspólna numeracja dokumentów dla kont Allegro należących do jednej firmy.
- **KSeF 2.0:** integracja z Krajowym Systemem e-Faktur, obsługa dokumentów FA(3), statusów wysyłki, numerów KSeF, UPO i kodów QR.
- **Dokumenty Allegro:** przekazywanie plików PDF faktur do zamówień przez właściwe konto sprzedawcy.
- **Obsługa wielu kont:** niezależna autoryzacja OAuth, synchronizacja zamówień i obsługa przesyłek dla każdego konta.
- **Historia i kopie zapasowe:** lokalna ewidencja dokumentów, przesyłek i operacji oraz tworzenie i weryfikacja kopii bezpieczeństwa.

## Architektura i bezpieczeństwo

Paura działa lokalnie na komputerze użytkownika, z wykorzystaniem interfejsu dostępnego w przeglądarce internetowej.

Każda instalacja posiada własną lokalną bazę danych SQLite, konfigurację firmy oraz dane uwierzytelniające. Instalacje nie współdzielą baz danych ani tokenów dostępu.

W ramach jednej instalacji obsługującej kilka kont Allegro:

- Każde konto sprzedawcy jest autoryzowane osobno.
- Zamówienia, przesyłki i operacje Allegro są przypisywane do właściwego konta.
- Dane firmy, numeracja faktur i integracja z KSeF są wspólne dla kont należących do tego samego podmiotu gospodarczego.
- Operacje wymagające zatwierdzenia podlegają odpowiednim kontrolom bezpieczeństwa.

Aplikacja komunikuje się z Allegro za pomocą oficjalnego **Allegro REST API** oraz protokołu **OAuth 2.0 Authorization Code**, a z KSeF za pomocą oficjalnego API KSeF 2.0.

Dostęp do każdego konta Allegro wymaga osobnej autoryzacji przez jego właściciela. Aplikacja nie wymaga przekazywania hasła do konta Allegro.

Dwie rodzinne instalacje mogą korzystać z jednej zarejestrowanej aplikacji deweloperskiej Allegro, zachowując niezależne autoryzacje sprzedawców.

## Status projektu

Wersja jednokontowa Paura jest już wykorzystywana w środowisku produkcyjnym do codziennej obsługi zamówień i przesyłek Allegro.

Rozwijana wersja obsługująca od jednego do trzech kont Allegro w jednej instalacji znajduje się na etapie końcowych testów i przygotowania do wdrożenia produkcyjnego.

Funkcjonalności wielokontowe, wystawianie dokumentów oraz integracje z Allegro i KSeF były weryfikowane w środowiskach testowych i za pomocą testów integracyjnych.

Docelowo obie niezależne instalacje będą korzystać z jednej wersji aplikacji Paura.

## Kontakt

W sprawach technicznych: **bloomnote.studio@gmail.com**

---

*Paura jest niezależnym projektem i nie stanowi oficjalnej aplikacji Allegro ani Ministerstwa Finansów.*

Repozytorium ma charakter wyłącznie informacyjny. Nie zawiera kodu źródłowego aplikacji, danych klientów, tokenów OAuth ani poufnych danych uwierzytelniających.
