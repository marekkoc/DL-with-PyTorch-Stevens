Chętnie wyjaśnię najważniejsze operacje związane ze strukturą i aktualizacją Twojego repozytorium Git.

## 1. Jak sprawdzić strukturę mojego repozytorium?

Aby sprawdzić strukturę repozytorium, możesz użyć kilku poleceń:

```bash
# Sprawdzenie lokalnych gałęzi
git branch

# Sprawdzenie wszystkich gałęzi (lokalnych i zdalnych)
git branch -a

# Sprawdzenie połączeń zdalnych (remote)
git remote -v

# Sprawdzenie aktualnego stanu i zmian
git status

# Wyświetlenie graficznej historii commitów
git log --graph --oneline --all --decorate
```

## 2. Jak pobierać zmiany z repozytorium głównego?

Aby pobierać zmiany z repozytorium głównego (upstream):

```bash
# Jeśli nie masz jeszcze skonfigurowanego upstream
git remote add upstream https://github.com/oryginalny-uzytkownik/oryginalny-projekt.git

# Pobierz zmiany z upstream (to tylko pobiera, ale nie scala)
git fetch upstream
```

## 3. Jak pobierać zmiany i aktualizować moje repozytorium?

Pełny proces aktualizacji Twojego forka:

```bash
# Krok 1: Upewnij się, że jesteś na właściwej gałęzi (np. master)
git checkout master

# Krok 2: Pobierz najnowsze zmiany z repozytorium głównego
git fetch upstream

# Krok 3: Scal zmiany z głównego repozytorium do Twojej lokalnej gałęzi
git merge upstream/master

# Krok 4: Wypchnij zaktualizowane zmiany do swojego forka
git push origin master
```

Jeśli pojawią się konflikty podczas scalania, Git powiadomi Cię o tym. Będziesz musiał je rozwiązać ręcznie, a następnie kontynuować proces scalania:

```bash
# Po rozwiązaniu konfliktów
git add .
git commit -m "Resolve merge conflicts"
git push origin master
```

Ta procedura utrzyma Twój fork zsynchronizowany z oryginalnym repozytorium, jednocześnie zachowując Twoje własne zmiany.
