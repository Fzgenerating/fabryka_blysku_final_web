# Jak spakować projekt do ZIP (bez pustego archiwum)

Masz dwa warianty w zależności od środowiska:

## Wymagania
Archiwum ZIP **nie jest trzymane w repozytorium**, aby uniknąć blokad przy
tworzeniu PR (platforma odrzuca duże pliki binarne). Do przygotowania paczki
we własnym środowisku potrzebujesz narzędzia `zip` (w systemach
Linux/macOS jest zwykle dostępne domyślnie; w Windows zainstalujesz je razem
z Git Bash lub możesz użyć PowerShell, patrz niżej).

## Windows (PowerShell)
1. Otwórz PowerShell w katalogu repozytorium.
2. Uruchom:
   ```powershell
   powershell -NoProfile -ExecutionPolicy Bypass -File .\package.ps1
   ```
3. Po zakończeniu pojawi się plik `fabryka_blysku.zip` (bez katalogu `.git`).

## Linux / macOS (bash)
1. W katalogu repozytorium wykonaj:
   ```bash
   ./package.sh
   ```
2. Powstanie plik `fabryka_blysku.zip` z pełną zawartością strony (bez `.git`).

Jeśli podczas rozpakowywania widzisz komunikat o pustym archiwum, upewnij się,
że skrypt był uruchomiony w katalogu projektu, pakowanie zakończyło się bez
komunikatów o błędach i że plik `.git` został wykluczony, a reszta plików była
dostępna.

> Uwaga: katalog `assets/img/gallery/slides/` został usunięty z repozytorium,
> aby nie wersjonować ciężkich plików binarnych – pozostała zawartość galerii
> znajduje się w paczce ZIP generowanej lokalnie. Plik `.gitignore`, który
> wcześniej wykluczał ten katalog, również został usunięty.
