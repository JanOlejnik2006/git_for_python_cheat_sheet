Markdown
# I. SETUP ŚRODOWISKA

## 1. Przygotowanie środowiska
- Utwórz konto na GitHubie na maila uczelni: [GitHub](https://github.com/)
- Pobierz i zainstaluj następujące narzędzia:
  - **MS Visual Studio Code:** [https://code.visualstudio.com/](https://code.visualstudio.com/)
  - W VS Code zaloguj się przez konto GitHub.
  - W zakładce Extensions wyszukaj i zainstaluj pakiet **Python** od MS (w który wchodzi Pylance, Python Environments i Python Debugger).
  - **Git:** [https://git-scm.com/](https://git-scm.com/)
  - **GitHub CLI (`gh`):**
    - Dla Mac wpisz w terminalu:
      ```bash
      /bin/bash -c "$(curl -fsSL [https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh](https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh))"
      brew install gh
      ```
    - Dla Windows wpisz w cmd:
      ```bash
      winget install --id GitHub.cli
      ```

## 2. Konfiguracja Gita (cmd lub terminal)
```bash
git config --global user.name "Twoje Imię"
git config --global user.email "twoj@email.com"

gh auth login
Wyklikaj w terminalu/cmd, żeby się zalogować przez przeglądarkę.

3. Tworzenie projektu, stawienie środowiska i łączenie go z gitem i GitHubem
Utwórz folder projektu w wybranej przez siebie lokalizacji.

Otwórz folder projektu w VS Code.

Otwórz terminal w VS Code (lewa góra, 4 ikonka od góry lub skrót Ctrl + `` ).

Wpisz w terminalu VS Code:

Dla Windows:

Bash
python -m venv .venv
Dla Mac / Linux:

Bash
python3 -m venv .venv
Utwórz w folderze projektu plik o nazwie .gitignore i wpisz do niego:

Plaintext
.venv/
__pycache__/
Utwórz repozytorium na gicie i GitHubie za pomocą terminala w VS Code:

Bash
git init
git branch -M main
gh repo create nazwa-repozytorium --public --source=. --remote=origin --push
Wejdź na GitHub w przeglądarkce na repo, które właśnie stworzyłeś.

Wjdź w Settings -> Collaborators i dodaj drugą osobę.

II. Praca na plikach
1. Pierwszy commit i wrzutka plików
Jak już stworzymy pliki i foldery, dodajemy je w terminalu:

git status – pokazuje nam, na jakim branchu jesteśmy, co jest w lokalnym repo i które pliki nie są dodane (przyda się mocno później do sprawdzania, na którym branchu jesteś):

Bash
git status
git add – dodaje pliki (jeśli damy po nim ., dodaje wszystko w folderze, w którym jesteśmy):

Bash
git add .
git commit – tworzy nowego commita (wersję) w lokalnym repo:

Bash
git commit -m "komentarz"
git push – wrzuca zcommitowaną wersję na repo na GitHubie:

Bash
git push
Sprawdź w przeglądarce, czy zmiany się pokazały.

2. Praca równoległa w dwie osoby (Branching & Pull Requests)
Żebyście nie nadpisali sobie nawzajem kodu w tym samym pliku, pracujcie na osobnych gałęziach (branches).

Pobieramy aktualną wersję z repo z GitHuba:

Bash
git pull origin main
Tworzymy własnego brancha (git checkout pozwala przełączać się między brachami, dopisek -b tworzy nowego brancha i przełącza od razu na niego):

Bash
git checkout -b Nazwa-brancha
Pozmieniaj pare rzeczy, możesz porobić zadania dalej czy coś – ważne, żeby coś się zmieniło.

Dodajemy zmiany do staging area i puszczamy commita:

Bash
git add .
git commit -m "komentarz"
Wrzucamy zmiany na GitHub na tym branchu:

Bash
git push origin Nazwa-brancha
Wejdź na GitHub w przeglądarce.

Kliknij zielony przycisk "Compare & pull request", a następnie zatwierdź (Create pull request -> Merge pull request), żeby połączyć swój kod z głównym branchem main.

Po złączeniu kodu, wróć do głównego brancha i pobierz najnowszy stan:

Bash
git checkout main
git pull origin main
III. Co zrobić, gdy pojawi się konflikt (Conflict)?
Jeśli przy git pull origin main lub git merge wyskoczy informacja o konflikcie, oznacza to, że Wy albo ktoś z pary edytowaliście tę samą linię w pliku.

Otwórz ten plik w VS Code – zobaczycie znaczniki konfliktów (<<<<<<<, =======, >>>>>>>).

Wybierzcie ręcznie, która wersja kodu ma zostać (usuwając niepotrzebne znaczniki), a następnie zróbcie normalnie:

Bash
git add .
git commit -m "fix: resolve merge conflict"
git push
IV. Co zrobić po ponownym włączeniu komputera (Codzienny start)?
Otwórz folder projektu w VS Code.

Otwórz terminal w VS Code.

Aktywuj wirtualne środowisko (.venv):

Dla Windows (PowerShell):

Bash
.venv\Scripts\Activate.ps1
Dla Windows (CMD):

Bash
.venv\Scripts\activate.bat
Dla Mac / Linux:

Bash
source .venv/bin/activate
Upewnij się, że po lewej stronie linii w terminalu pojawił się napis (.venv).

Pobierz najnowszy stan z GitHuba, upewniając się, że jesteś na głównym branchu:

Bash
git checkout main
git pull origin main


