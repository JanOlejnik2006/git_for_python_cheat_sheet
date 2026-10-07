I SETUP SRODOWISKA 

1 przygotowanie srodowiska

- utworz konto na githubie na maila uczelni
https://github.com/

- pobierz nastepujace:

- MS Visual Studio Code:
https://code.visualstudio.com/

- W VSC zaloguj sie przez konto githuba

- W extensions wyszukaj i zainstaluj pakiet Python od MS w ktory wchodzi Pylance, Python Enviroments i Python Debugger

- Git:
https://git-scm.com/

- GitHub CLI:
- Dla Mac wpisz w terminalu
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install gh

- Dla Windows wpisz w cmd
winget install --id GitHub.cli


2 konfiguracja gita (cmd lub terminal)

git config --global user.name "Twoje Imię"
git config --global user.email "twoj@email.com"

gh auth login
- wyklikaj w terminalu/cmd zeby sie zalogowac przez przegladarke

3 tworzenie projektu, stawienie srodowiska i laczenie go z gitem i githubem 

- utworz folder projektu w wybranej przez siebie lokalizacji
- otworz folder projektu w vsc
- otworz terminal w vsc (lewo gora 4 od gory ikonka i tam jest)

- wpisz w terminalu VS Code:

- Dla Windows: 
python -m venv .venv

- Dla Mac / Linux: 
python3 -m venv .venv

- utworz w folderze projektu plik o nazwie .gitignore i wpisz do niego:
.venv/
__pycache__/

- utworz repozytorium na gicie i githubie za pomoca terminala w vsc
git init
git branch -M main
gh repo create nazwa-repozytorium --public --source=. --remote=origin --push

- wejdz na githuba na przegladarce w repo ktore wlasie stworzyles 
- w ustawienia, w collaborators i dodaj druga osobe

II praca na plikach
1 najpierw zajmiemy sie stworzeniem tych plikow i folderow ktore byly w instrukcji zeby zrobic pierwszy commit i wrzucic juz cos na githuba
- jak juz stworzymy pliki to dodajemy je w terminalu
- git status pokazuje nam na jakim branchu jestesmy co jest w lokalnym repo i ktore pliki nie sa dodane(przyda sie mocno pozniej do sprawdzania na ktorym branchu jestes)
git status

- git add dodaje, jak dodany po nim . lub -A to dodaje wszystko w folderze w ktorym jestsmy
git add .

- git commit tworzy nowego commita(wersje) w lokalnym repo
git commit -m "komentarz"

- git push wrzuca zcommitowana wersje na repo na githubie
git push

- sprawdz w przegladarce czy zmiany sie pokazaly

2 teraz zajmiemy sie juz praca na plikach w dwie osoby
- Praca równoległa w dwie osoby (Branching & Pull Requests)
- Żebyście nie nadpisali sobie nawzajem kodu w tym samym pliku, pracujcie na osobnych gałęziach (branches)

- pobieramy aktualna wersje z repo z githuba
git pull origin main

- tworzymy wlasnego brancha (git checkout pozwala przelaczac sie miedzy branchaim, dopisek -b tworzy nowego brancha i przelacza od razu na niego)
git checkout -b Nazwa-brancha

- pozmieniaj pare rzeczy mozesz porobic zadania dalej czy cos wazne zeby cos sie zmienilo

- dodajemy zmiany do staging area i puszczamy commita
git add .
git commit -m "komentarz"

- wrzucamy zmiany na githuba na tym branchu
git push origin Nazwa-brancha

- Wejdź na GitHub w przeglądarce.
- Kliknij zielony przycisk "Compare & pull request", a następnie zatwierdź (Create pull request -> Merge pull request), żeby połączyć swój kod z głównym branchem main.

- Po złączeniu kodu, wróć do głównego brancha i pobierz najnowszy stan:
git checkout main
git pull origin main



III Co zrobić, gdy pojawi się konflikt (Conflict)?

- Jeśli przy git pull origin main lub git merge wyskoczy informacja o konflikcie, oznacza to, że Wy albo ktoś z pary edytowaliście tę samą linię w pliku.

- Otwórz ten plik w VS Code – zobaczycie znaczniki konfliktów (<<<<<<<, =======, >>>>>>>).

- Wybierzcie ręcznie, która wersja kodu ma zostać (usuwając niepotrzebne znaczniki), a następnie zróbcie normalnie:
git add .
git commit -m "fix: resolve merge conflict"
git push

IV Co zrobić po ponownym włączeniu komputera (Codzienny start)?

- Otwórz folder projektu w VS Code.
- Otwórz terminal w VS Code.
- Aktywuj wirtualne środowisko (.venv)
- Dla Windows (CMD): 
.venv\Scripts\activate.bat

- Dla Mac / Linux: 
source .venv/bin/activate

- Upewnij się, że po lewej stronie linii w terminalu pojawił się napis (.venv).

- Pobierz najnowszy stan z GitHuba, upewniając się, że jesteś na głównym branchu:
git checkout main
git pull origin main

- reszta dziala tak jak wczesniej 
- chechout tworzymy brancha
- add .  dodajemy pliki
- commit commitujemy
- push origin Nazwa-brancha pushujemy brancha
- w przegladarce mergujemy
