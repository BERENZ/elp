
# Kontrola wersji {#kontrola-wersji}

<!-- https://peerj.com/preprints/3159/ -->
<!-- https://swcarpentry.github.io/git-novice/ -->
<!-- https://arxiv.org/pdf/1811.02021.pdf -->
<!-- http://happygitwithr.com/ -->
<!-- https://whattheyforgot.org/ -->
<!-- https://education.github.com/git-cheat-sheet-education.pdf -->
<!-- https://enterprise.github.com/downloads/en/github-flow-cheatsheet.pdf -->

Systemy kontroli wersji to narzędzia pozwalające na zapamiętywaniu zmian zachodzących w plikach.
Dzięki nim możemy sprawdzić nie tylko kiedy zmieniliśmy dany plik i kto go zmienił, ale co najważniejsze - możemy linia po linii prześledzić zmiany wewnątrz tego pliku.
Dodatkowo, mamy możliwość przywracania wersji pliku z wybranego czasu w całej historii jego zmian.

Systemy kontroli wersji są bardzo powszechnie wykorzystywane przy tworzeniu wszelakiego rodzaju oprogramowania.
Wynika to nie tylko z ich zalet wymienionych powyżej, ale również rozbudowanych możliwości pozwalających na współpracę wielu osób nad jednym projektem.

Istnieje wiele systemów kontroli wersji różniących się zarówno używaną terminologią, sposobem działania czy możliwościami.^[https://en.wikipedia.org/wiki/Comparison_of_version-control_software#History_and_adoption]
Współcześnie najbardziej popularnym systemem kontroli jest Git, któremu będzie poświęcona reszta tego rozdziału.
Inne popularne systemy kontroli wersji to Concurrent Versions System (CVS), Mercurial czy Subversion (SVN).

<!-- gdzie wykorzystywaneC -->
<!-- block - large files -->

## Git

System Git jest niezależny od języka (lub języków) programowania, które używamy.
Jego działanie oparte jest o system komend rozpoczynających się od słowa `git `, które należy wykonać w systemowym oknie konsoli.^[Nie w oknie konsoli R.]
Zrozumienie działania systemu Git wymaga także poznania kilku nowych terminów.

Git składa się z kilkudziesięciu komend, których działanie jest dalej uzależnione od podanych argumentów.
Tutaj przedstawiony zostanie tylko podzbiór najczęściej używanych.
Pełniejszy opis komend systemu Git można znaleźć pod adresem https://education.github.com/git-cheat-sheet-education.pdf lub http://rogerdudler.github.io/git-guide/index.pl.html.

<!-- git clients -->

### Konfiguracja systemu Git

Kolejnym krokiem po instalacji systemu Git^[Instrukcje dotyczące instalacji Gita znajdują się we wstępie książki.] jest jego konfiguracja. 
Można ją wykonać używając wbudowanego terminala (Mac OS i Linux) lub terminala dodanego podczas instalacji systemu Git (Windows).
Polega ona na podaniu nazwy użytkownika (np. "Imie Nazwisko") oraz jego emaila ("email@portal.com").


```bash
git config --global user.name "imie nazwisko"
git config --global user.email "email"
```

### Repozytorium

<!-- co to repo -->
Podstawowym z nich jest repozytorium (ang. *repository*, często określane skrótowo jako repo).
Jest to folder, który przechowuje wszystkie pliki i foldery w ramach jednego projektu.^[W kontekście R, warto o tym myśleć jako o projekcie RStudio.]
Dodatkowo wewnątrz repozytorium znajduje się ukryty folder `.git`, który zawiera informację o historii i zmianach każdego z naszych plików.
Repozytorium może znajdować się na dysku naszego komputera (wtedy jest nazywane repozytorium lokalnym) lub też na serwerze w internecie (określane jako repozytorium zdalne (ang. *remote*)).
Istnieje wiele serwisów internetowych pozwalających na tworzenie, przechowywanie i edycję repozytoriów zdalnych, między innymi [GitHub](https://github.com/) (przybliżony w sekcji \@ref(github)), [GitLab](https://gitlab.com/), czy [BitBucket](https://bitbucket.org/).


```bash
# określenie obecnego katalogu jako repozytorium Git
git init                  
```

### Dodawanie zmian

Po dodaniu zmian są one przechowywane w miejscu określanym jako *Index*.
Działa ono jak poczekalnia - w tym momencie zmiany jeszcze nie są potwierdzone, ale możemy sprawdzić co zmieniło się od ostatniego zatwierdzenia zmian.


```bash
# dodanie pojedynczego pliku
git add sciezka_do_pliku  
# dodanie wszystkich plików 
git add --all                    
```

### Sprawdzanie zmian

Zanim zatwierdzimy zmiany możemy je sprawdzić.
W ten sposób można dla każdej linii tekstu dowiedzieć się co zostało dodane lub usunięte.


```bash
# sprawdzenie dodanych zmian
git diff                  
```

### Zatwierdzanie zmian

Zatwierdzanie zmian (ang. **commit**) powoduje ich zapisanie w systemie Git.
Wymaga to dodania wiadomości, która opisuje wprowadzone zmiany.
<!-- https://chris.beams.io/posts/git-commit/ -->
<!-- https://thoughtbot.com/blog/5-useful-tips-for-a-better-commit-message -->
<!-- https://github.com/erlang/otp/wiki/writing-good-commit-messages -->
<!-- https://code.likeagirl.io/useful-tips-for-writing-better-git-commit-messages-808770609503 -->
<!-- HEAD -->


```bash
# zawierdzenie dodanych zmian
git commit -m "opis wprowadzonych zmian"
```

### Rozgałęzienia


```bash
# wypisanie wszystkich rozgałęzień
git branch
```


```bash
# utworzenienie nowego rozgałęzienia
git branch nazwa_nowej_galezi
```


```bash
# przejście do innego rozgałęzienia
git checkout nazwa_innej_galezi
```


```bash
# połączenie wybranego rozgałęzienia z obecnym
git merge nazwa_nowej_galezi
```

### Repozytorium zdalne


```bash
# pobranie kopii istniejącego zdalnego repo
git clone sciezka_do_zdalnego_repo
```

<!-- ssh vs https -->


```bash
# dodanie ścieżki do zdalnego repo
git remote add origin sciezka_do_zdalnego_repo
```

<!-- zmiana z git remote set-url origin git@github.com:User/UserRepo.git -->

### Wysyłanie zmian


```bash
# wysyłanie zmian do zdalnego repo
git push
```

<!-- co to push -->

### Aktualizowanie 


```bash
# aktualizowanie zmian ze zdalnego repo
git pull
```

## GitHub

GitHub jest serwisem internetowym pozwalającym na przechowywanie i interakcję z repozytoriami w systemie kontroli wersji Git.


<!-- co to pull request -->
<!-- lista podsatwowych komend -->
<!-- create a ssh key -->



Oprócz dostępu do kodu i jego zmian, GitHub oferuje szereg dodatkowych możliwości.
<!--..-->
<!-- https://en.wikipedia.org/wiki/GitHub#Scope -->




## Git w RStudio

<!-- Use a Git client, if you like -->
<!-- workflow -->

## Sposób pracy

<!-- podstawowy workflow -->
<!-- when something go wrong -->
<!-- stackoverflow git questions -->

## Zadania

<!-- stwórz najprostszą stronę internetową -->