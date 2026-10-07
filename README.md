1 przygotowanie srodowiska

utworz konto na githubie na maila uczelni
https://github.com/

pobierz nastepujace:

MS Visual Studio Code:
https://code.visualstudio.com/

W VSC zaloguj sie do 

Git:
https://git-scm.com/

GitHub CLI:
Dla Mac
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install gh

Dla Windows 
winget install --id GitHub.cli


2 konfiguracja gita

git config --global user.name "Twoje Imię"
git config --global user.email "twoj@email.com"

gh auth login

