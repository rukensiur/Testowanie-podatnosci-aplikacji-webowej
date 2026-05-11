Automatyzacja polegała na stworzeniu skryptu w pythonie dzięki któremu proces skanowania za pomocą ZAP jest szybszy. 

Opis działania skryptu:

1. Konfiguracja API ZAP

2. Start ZAP w tle (Daemon Mode)

3. Uruchomienie modułu Spider

4. Uruchomienie skanowania aktywnego

5. Generowanie raportu w pdf

6. Wyłączenie ZAP i zakończenie działania skryptu



Porównanie czasów wykonywania ręcznie a automatycznie:

Czas wykonywania skanowania ręcznie w przybliżeniu wyniósł 4 minuty 15 sekund.
Czas wykonywania skanowania przy użyciu skryptu wyniósł 2 minuty 3 sekundy.