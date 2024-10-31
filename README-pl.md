Dziękuję za zwrócenie uwagi! Oto poprawiony README z uwzględnieniem wszystkich ścieżek frontendu:

---

# Scool Corner

## Wprowadzenie
Scool Corner to aplikacja internetowa stworzona do zarządzania darowiznami i wypłatami oraz monitorowania ich w czasie rzeczywistym. Projekt łączy sponsorów i uczniów, umożliwiając sponsorowanie różnych produktów dla uczniów. Aplikacja składa się z backendu opartego na Node.js, Express oraz Sequelize (do zarządzania bazą danych) oraz frontendowej części React, która wykorzystuje Socket.IO do obsługi aktualizacji na żywo.

## Spis Treści
- [Wprowadzenie](#wprowadzenie)
- [Funkcje](#funkcje)
- [Użyte technologie](#użyte-technologie)
- [Instalacja](#instalacja)
- [Konfiguracja](#konfiguracja)
- [Użycie](#użycie)
- [Ścieżki i Endpointy](#ścieżki-i-endpointy)
- [Współtworzenie](#współtworzenie)
- [Licencja](#licencja)

## Funkcje
- **Aktualizacje w czasie rzeczywistym**: Socket.IO obsługuje powiadomienia na żywo o darowiznach i wypłatach.
- **Zarządzanie darowiznami**: Śledzenie darowizn od sponsorów i ich wyświetlanie na żywo.
- **Monitorowanie wypłat**: Obserwacja wypłat z miesięcznym raportem i aktualnym stanem konta.
- **Funkcje administracyjne**: Panel administracyjny do zarządzania przedmiotami, sponsorami i produktami.
- **Responsywny frontend**: UI w React z animacjami, bieżącymi aktualizacjami i wyświetlaniem sponsorów.

## Użyte technologie
- **Backend**: Node.js, Express, Sequelize (MySQL/MariaDB)
- **Frontend**: React, Socket.IO, Framer Motion (do animacji)
- **Inne**: Axios, dotenv do konfiguracji środowiska, CORS do zapytań między domenami.

## Instalacja

### Wymagania
- **Node.js**: Wymagana jest instalacja Node.js (rekomendowana wersja 12+).
- **MySQL/MariaDB**: Instalacja i konfiguracja bazy danych MySQL lub MariaDB.

### Backend
1. Sklonuj repozytorium i przejdź do folderu backendu:
   ```bash
   git clone <repository-url>
   cd backend
   ```

2. Zainstaluj zależności:
   ```bash
   npm install
   ```

3. Skonfiguruj zmienne środowiskowe, tworząc plik `.env` w głównym katalogu backendu:
   ```bash
   PORT=3001
   DATABASE_URL=<twoj-url-bazy-danych>
   ```

4. Skonfiguruj połączenie z bazą danych w pliku `config/config.json`:
   ```json
   {
     "development": {
       "username": "twoja_nazwa_uzytkownika",
       "password": "twoje_haslo",
       "database": "nazwa_bazy_danych",
       "host": "127.0.0.1",
       "dialect": "mysql"
     }
   }
   ```

5. Uruchom migracje bazy danych:
   ```bash
   npx sequelize-cli db:migrate
   ```

6. Uruchom serwer backendu:
   ```bash
   npm start
   ```

### Frontend
1. Przejdź do katalogu frontend:
   ```bash
   cd frontend
   ```

2. Zainstaluj zależności frontendu:
   ```bash
   npm install
   ```

3. Stwórz plik `.env` w katalogu frontend:
   ```bash
   REACT_APP_API_URL=http://localhost:3001
   REACT_APP_WS_URL=http://localhost:3001
   ```

4. Uruchom serwer deweloperski frontendu:
   ```bash
   npm start
   ```

## Konfiguracja

- **Backend**: Skonfiguruj zmienne środowiskowe w pliku `.env` dla backendu oraz konfigurację bazy danych w `config/config.json`.
- **Frontend**: Skonfiguruj punkty API oraz WebSocket w pliku `.env` frontendu, jak opisano w sekcji instalacji.

## Użycie

1. Uruchom oba serwery - backend i frontend - zgodnie z instrukcjami instalacji.
2. Przejdź do aplikacji pod adresem `http://localhost:3000`.
3. **Logowanie**: Zaloguj się lub zarejestruj jako administrator lub sponsor, aby uzyskać pełen dostęp.
4. **Aktualizacje na żywo**: Obserwuj aktualizacje o darowiznach i wypłatach wyświetlane w czasie rzeczywistym na frontendzie.

## Ścieżki i Endpointy

### Endpointy API Backend
| Ścieżka                 | Metoda | Opis                                 |
|-------------------------|--------|--------------------------------------|
| `/products`             | GET    | Pobiera listę produktów             |
| `/donations`            | GET    | Pobiera listę darowizn              |
| `/withdrawals`          | GET    | Pobiera listę wypłat                |
| `/school-subjects`      | GET    | Pobiera aktualny przedmiot miesiąca |
| `/auth`                 | POST   | Autoryzacja użytkownika             |

### Ścieżki Frontendu
| Ścieżka                  | Opis                                          |
|--------------------------|-----------------------------------------------|
| `/`                      | Strona główna z danymi darowizn               |
| `/donate`                | Strona dodawania darowizn                     |
| `/withdraw`              | Strona dodawania wypłat                       |
| `/sponsor`               | Strona dodawania sponsora                     |
| `/school-subject`        | Strona zmiany przedmiotu miesiąca             |
| `/admin`                 | Panel administracyjny                         |
| `/edit-or-delete`        | Strona edycji lub usuwania wpisów             |
| `/edit-products`         | Strona edycji produktów                       |
| `/login`                 | Strona logowania                             |

## Współtworzenie
1. Stwórz fork repozytorium.
2. Utwórz nową gałąź (`git checkout -b feature/NowaFunkcjonalnosc`).
3. Wprowadź zmiany (`git commit -am 'Dodaj nową funkcję'`).
4. Wyślij zmiany na gałąź (`git push origin feature/NowaFunkcjonalnosc`).
5. Otwórz pull request.

## Licencja
Projekt jest licencjonowany na licencji MIT.
