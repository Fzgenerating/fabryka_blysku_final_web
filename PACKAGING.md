# Jak spakować projekt do ZIP (bez pustego archiwum)

Masz dwa warianty w zależności od środowiska:

## Wymagania
Potrzebujesz narzędzia `zip` (w systemach Linux/macOS jest zwykle dostępne
domyślnie; w Windows zainstalujesz je razem z Git Bash lub możesz użyć
PowerShell, patrz niżej).

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
   Plik ZIP nie jest trzymany w repozytorium (unikamy ostrzeżeń o plikach
   binarnych w PR), więc po pobraniu projektu wygeneruj go lokalnie powyższym
   skryptem.

Jeśli podczas rozpakowywania widzisz komunikat o pustym archiwum, upewnij się,
że skrypt był uruchomiony w katalogu projektu, pakowanie zakończyło się bez
komunikatów o błędach i że plik `.git` został wykluczony, a reszta plików była
dostępna.
