Wykonalismy kolejny skan przy uzyciu ZAP. Po przeprowadzeniu analizy ryzyka postanowilismy wyeliminowac nastepujace zagrozenia: Missing Anti-clickjacking Header, SQL Injection.


Analiza Ryzyka: Missing Anti-clickjacking Header.

Prawdopodobieństwo: Wysokie. 
Jeśli nagłówka brakuje, błąd jest dostępny z zewnątrz dla każdego. Atakujący musi jedynie przygotować złośliwą stronę, która „opakuje” Juice Shop w niewidoczną ramkę.

Wpływ: Średni. 
Atak wymaga interakcji użytkownika (musi on wejść na stronę atakującego i coś kliknąć). Skutkiem może być np. nieświadome usunięcie konta przez użytkownika lub zmiana ustawień profilu.

Argumentacja: 
Choć błąd jest trywialny do wykrycia przez skanery (jak ZAP), jego skuteczne wykorzystanie zależy od socjotechniki. W Juice Shopie clickjacking mógłby pozwolić na „zakupy” na koszt zalogowanego użytkownika, ale nie daje bezpośredniego dostępu do serwera.

Analiza Ryzyka: SQL Injection.
Prawdopodobieństwo: Wysokie. Skoro ZAP wykrył to w Juice Shopie, oznacza to, że istnieją nieprzefiltrowane punkty styku z bazą danych. Atakujący może użyć gotowych narzędzi (np. sqlmap), aby zautomatyzować proces.

Wpływ: Krytyczny. 
SQLi pozwala na: Wykradzenie całej bazy użytkowników (maile, hasła). Zalogowanie się na dowolne konto (nawet admina) bez znajomości hasła. Modyfikację cen produktów lub usuwanie danych.

Argumentacja:
To błąd typu „klucze do królestwa”. Atakujący nie potrzebuje interakcji użytkownika – uderza bezpośrednio w serce aplikacji (dane). W świecie rzeczywistym taki błąd to niemal gwarantowany wyciek danych (Data Breach) i ogromne kary finansowe.


Ponowny Skan

Wdrożyliśmy poprawki w kodzie i przeprowadziliśmy kolejny skan przy użyciu ZAP, który potwierdził naprawienie błędu. 


