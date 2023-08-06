### Strategia branchowania

1. Głównymi branchami projektu są:
  - master
  - develop
  - inne branche odchodzące od develop, na których implementowane są zadania
2. Branch 'master' jest głównym branchem aplikacji, do niego można jedynie merge'ować kod
z branch'a 'develop', gdy zespół zmienia znacznie wersje i funkcjonalności aplikacji
3. Branch 'develop' jest branchem z gotowym i przetestowanym kodem platformy, mergowane
są do niego inne podrzędne branche z zadaniami dodające nowe funkcjonalności do 'develop',
nie wolno do niego bezpośrednio push'ować, lub commit'ować żadnego kodu
4. Inne branch'e tzw. feature, na nich zespół bezpośrednio pracuje i dodaje tam kod,
przy etapie dodawania nowych funkcjonalności do branch'a develop, wystawia się pull request
i po przetestowaniu rozwiązania jest on merge'owany do 'develop', a stary branch jest usuwany.
5. Przykładowy scenariusz:
  - muszę dodać nowy ekran do aplikacji
  - tworzę nowego brancha 'new-screen-app' odchodząc od gałęzi 'develop'
  - wprowadzam zmiany na branch'u 'new-screen-app'
  - po dodaniu wszystkich zmian wystawiam pull request
  - po Code Review i zaakceptowaniu zmian, robię merge branch'a 'new-screen-app',
    do gałęzi 'develop'
  - usuwam starą gałąź 'new-screen-app'

### Strategia commit'owania

1. Commit'y tworzy się w oparciu o następujący schemat (po angielsku):
  - type: commit description
2. Następujące typy 'type' podawane przy różnego rodzaju commit'ach:
  - 'feat' - opisuje nową funkcjonalność dodawaną do aplikacji
  - 'fix' - poprawa błędu występującego w kodzie
  - 'test' - testowanie dowolnej funkcjonalności
  - 'docs' - dodawanie opisów, komentarzy do kodu
  - 'refactor' - refaktorowanie kodu
3. Przykłady commit'ów:
  - Dodanie przycisku do apki: 'feat: add button to app main page'
  - Naprawa wyświetlania tekstu w aplikacji: 'fix: fix showing text in app main page'
  - Modyfikacja README w repo: 'docs: edit readme'
  - Test strony w aplikacji: 'test: add test for main app page'
  - Duży refaktor kodu aplikacji: 'refactor: migrate flutter app to new version of flutter'

### Strategia Pull/Merge Request i Code Review

1. Wystawianie PR i MR jest obowiązkowe przy merge'owaniu branchy do 'develop'
i z 'develop' do 'master'
2. Tytuł wystawianego PR powinien mieć w nazwie ID oraz nazwę (lub informację o głównej funkcjonalności) zadania w Jirze,
przykładowo - '[LIT-9] Implementacja modułu do wyświetlania analiz na podstawie śmieci'
3. Do wystawianego PR powinien być dołączony 1 recenzent (reviewers), gdzie recenzent nie może być autorem kodu.
4. PR jest gotowy do merge'owania, gdy recenzent sprawdzi kod pod względem poprawności uruchamiania i zaakceptuje PR (approve)
