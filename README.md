# Usługa teleporady

Projekt ma na celu zarządzanie dokumentacją związaną z wdrożeniem nowej usługi medycznej "Telekonsultacje zdrowotne" przy użyciu systemu kontroli wersji GIT oraz GitHub. 

Główne cele projektu:
- Utworzenie repozytorium zarządzającego dokumentacją projektu.
- Wdrożenie podstawowych funkcji GIT, takich jak śledzenie zmian, tworzenie gałęzi, scalanie oraz korzystanie ze zdalnego repozytorium.
- Symulacja zespołowej pracy nad dokumentacją.

Repozytorium zawiera dokumenty opisujące usługę, plan wdrożenia, analizę ryzyk oraz plany marketingowe i ankiety dla pacjentów.

## Użyte polecenia GIT

- `git init` – Utworzenie lokalnego repozytorium.
- `git add <plik>` – Dodanie plików do indeksu.
- `git commit -m "opis"` – Zatwierdzanie zmian w repozytorium z opisem.
- `git branch <nazwa>` – Utworzenie nowej gałęzi.
- `git checkout <nazwa>` – Przełączanie się między gałęziami.
- `git merge <gałąź>` – Scalanie zmian z wybranej gałęzi do obecnej.
- `git tag -d` <opis> - Usunięcie aktualnego tagu
- `git tag -m "opis" v1.0` – Dodanie tagu v1.0 do repozytorium.
- `git push` – Wysyłanie zmian do zdalnego repozytorium.
- `git merge marketing --no-ff -m "Scalono gałąź marketing z główną gałęzią"` - Komenda scala dwie gałęzie, dokumentując to w historii w sposób czytelny i jednoznaczny. 



## Instrukcje pracy z repozytorium

### Klonowanie repozytorium
Aby sklonować repozytorium na swój komputer, użyj polecenia:
```bash
git clone https://github.com/joajas-ada/new_service_PD4336.git
```

---

## **Napotkane problemy i ich rozwiązania**

### Problem 1: Problem przy scalaniu gałęzi
**Opis problemu:** Podczas scalania gałęzi `marketing` z główną w edytorze VS Code i potrzebą udokumentowania tego kroku w historii w sposób czytelny i jednoznaczny użycie kodu:
```bash
git merge marketing -m "Scalono gałąź marketing z główną gałęzią"
```
spowodowało, że przebycie tego kroku nie było widoczne w mapie commitów. Wyświetlił się również następujący komunikat: `Fast-forward (no commit created; -m option ignored)`. Rozwiązanie problemu `Fast-forward` umożliwiło przestudiowanie dokumentacji na stronie (https://git-scm.com/docs/git-merge) 

#### Znaleziono rozwiązanie w postaci kodu:
```bash
git merge marketing --no-ff -m "Scalono gałąź marketing z główną gałęzią"
```



### Problem 2: Problem z przypisywaniem atrybutów
**Opis problemu:** Podczas przygotowywania projektu nastąpił problem z właściwą konfiguracją GIT tak, aby traktował plik .jpg jako binarny
Rozwiązanie problemu umożliwiło przestudiowanie dokumentacji na stronie: (https://git-scm.com/docs/gitattributes) i zapisanie w pliku `.gitattributes` informacji `*.jpg binary`




### Problem 3: Problem z poprawnym tagowaniem w VS Code
**Opis problemu:** Podczas próby tagowania commitu z obrazkiem kotka przez edytor VS Code, nastąpiło wprowadzenie doodatkowych znaków `-` w sposób niezamierzony: `tag: v1.0---Gotowy-plan-wdrożenia-usługi-medyczneożenia-usługi-medyczne`. 
Tak jak poprzednio rozwiązanie problemu było możliwe poprzez przestudiowanie manuala: (https://git-scm.com/docs/git-tag).

Na początku używając kodu: 
```bash
git tag -d v1.0---Gotowy-plan-wdrożenia-usługi-medyczne
```
możliwym było usunięcie poprzedniego tagu.

#### Znaleziono rozwiązanie w postaci kodu:
```bash
git tag -m "Gotowy plan wdrożenia usługi medycznej" v1.0
```
