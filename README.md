# WebScreenShare — pobieranie

Udostępnianie ekranu lub okna do przeglądarki widza. Bez instalacji: pobierz, rozpakuj, uruchom.

## Pobierz

Najnowsza paczka: **[Releases](../../releases/latest)** → plik `WebScreenShare-<wersja>-win-x64.zip`.

1. Rozpakuj zip do dowolnego folderu (np. `C:\WebScreenShare`). Nie do `Program Files`, bo aplikacja
   aktualizuje się sama i potrzebuje prawa zapisu w swoim folderze.
2. Uruchom `WebScreenShare.exe`. Przy pierwszym starcie Windows zapyta o zgodę na reguły zapory (UAC).
3. Wybierz ekran lub okno, skopiuj link z nagłówka i prześlij widzowi.

## Jak dociera obraz

- **Link przez serwer (Relay)** — działa zawsze, także bez otwierania portów na routerze. Paczka ma
  już wpisany serwer pośredniczący, więc link „Relay" pojawia się sam po starcie. Obraz jest
  szyfrowany end-to-end (klucz jest w linku po znaku `#`, serwer go nie widzi).
- **P2P** — gdy to możliwe, przeglądarka widza łączy się bezpośrednio z Twoim komputerem (szybciej).
- **Link bezpośredni (External/DynDNS)** — gdy masz otwarty port (UPnP lub ręcznie).

## Aktualizacje

Aplikacja sprawdza nowe wydania po starcie i raz dziennie. Nową wersję instaluje po kliknięciu
„Aktualizuj"; paczka jest weryfikowana sumą SHA-256 z pliku `.sha256` obok zipa. W trybie
zaawansowanym można włączyć aktualizację automatyczną (gdy nikt nie ogląda). Poprzednia wersja
zostaje w folderze jako `WebScreenShare-<wersja>-<data>.exe.old` — powrót to zmiana nazwy pliku.

## Pliki w paczce

`WebScreenShare.exe`, `settings.ini` (ustawienia; edytowalne), `CHANGELOG-user.txt` (co nowego),
`HELP.md` (opis wszystkich opcji, także dla asystentów AI).

## Weryfikacja paczki

```powershell
(Get-FileHash .\WebScreenShare-<wersja>-win-x64.zip -Algorithm SHA256).Hash
```

Wynik musi być równy pierwszemu słowu w pliku `WebScreenShare-<wersja>-win-x64.zip.sha256`.
