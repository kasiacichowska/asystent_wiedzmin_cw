# Wiedźmiński Asystent AI

Aplikacja webowa zrobiona w Pythonie i Flasku, która korzysta z Claude (Anthropic).

Aplikacja jest utrzymana w klimacie Wiedźmina. Użytkownik może zadawać pytania wiedźmińskiemu asystentowi, przesyłać pliki PDF do analizy oraz streszczać tekst.

## Funkcje

- Czat z Claude w klimacie Wiedźmina
- Analiza i podsumowanie plików PDF
- Streszczanie wpisanego tekstu
- Rejestracja i logowanie użytkowników
- Hasła hashowane przez bcrypt
- Ograniczenie liczby zapytań
- Podstawowa ochrona przed prompt injection
- Ograniczenie wielkości przesyłanego pliku PDF do 5 MB

## Wymagania

- Python 3.10 lub nowszy
- Konto Anthropic i klucz API do Claude
- Git, jeśli projekt ma być klonowany z GitHuba

## Instalacja lokalna

1. Sklonuj repozytorium:

```bash
git clone https://github.com/kasiacichowska/asystent_wiedzmin_cw.git
cd asystent_wiedzmin_cw
```

2. Stwórz wirtualne środowisko:

```bash
python -m venv venv
```

3. Aktywuj wirtualne środowisko.

Windows:

```bash
venv\Scripts\activate
```

Linux / macOS:

```bash
source venv/bin/activate
```

4. Zainstaluj potrzebne biblioteki:

```bash
pip install -r requirements.txt
```

5. Stwórz plik `.env` w głównym folderze projektu i uzupełnij:

```env
ANTHROPIC_API_KEY=twoj-klucz-tutaj
SECRET_KEY=dowolny-dlugi-losowy-tekst
```

6. Uruchom aplikację:

```bash
python app.py
```

7. Otwórz w przeglądarce:

```text
http://127.0.0.1:5000
```

Po uruchomieniu można utworzyć konto, zalogować się i korzystać z funkcji aplikacji.

## Zmienne środowiskowe

| Nazwa | Opis | Wymagana |
| --- | --- | --- |
| `ANTHROPIC_API_KEY` | Klucz API potrzebny do korzystania z Claude | Tak |
| `SECRET_KEY` | Sekret używany przez Flask do obsługi sesji użytkownika | Tak |


## Struktura projektu

```text
asystent_wiedzmin_cw/
├── app.py                 główny plik aplikacji
├── requirements.txt       lista potrzebnych bibliotek
├── README.md              opis projektu i instrukcja uruchomienia
├── templates/             pliki HTML
│   ├── index.html
│   ├── analiza.html
│   ├── streszcz.html
│   ├── logowanie.html
│   └── rejestracja.html
└── static/                pliki wyglądu i grafiki
    ├── style.css
    └── img/
        └── medalion.webp
```

Po zarejestrowaniu pierwszego użytkownika aplikacja tworzy również plik `users.json`, w którym przechowywane są dane kont użytkowników.

## Znane ograniczenia

- Dane użytkowników są zapisywane w pliku `users.json` zamiast w prawdziwej bazie danych.
- Aplikacja nie zapisuje historii rozmów z asystentem.
- Analizowane są tylko pliki PDF zawierające tekst, więc skan dokumentu bez odczytywalnego tekstu może nie zadziałać poprawnie.
- Do działania funkcji AI potrzebne jest połączenie z internetem i poprawny klucz API Anthropic.
- Jest to projekt edukacyjny, dlatego nie wszystkie elementy są przygotowane tak jak w dużej aplikacji produkcyjnej.

## Autor

Kasia Cichowska - projekt stworzony w ramach kursu Career Wings Mazovia.
