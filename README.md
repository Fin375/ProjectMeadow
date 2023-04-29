# ProjecyMeadow
Simulation based on object-oriented programming, dependencies between object classes and the use of java swing for simple animation.

Temat: Symulacja łąki

Łąka jest planszą o zadanym rozmiarze, na której rosną różne rodzaje kwiatów. Rodzaje kwiatów to klasy dziedziczące po klasie ogólnej Kwiaty, zawierającą podstawowe parametry. Klasy dziedziczące zawierają metody określające jak dany rodzaj oddziałuje na pszczoły (np. jedne kwiaty dają 2 razy więcej nektaru niż inne). Po planszy przemieszczają się pszczoły oraz szerszenie, wchodzą one ze sobą w interakcje. Szerszeń jest wrogiem pszczoły i może ją zaatakować - usunąć obiekt. Jednakże jednoczesne spotkanie szerszenia i dwóch pszczół eliminuje obiekt szerszenia. Celem pszczół jest uzyskanie jak największej ilości nektaru z kwiatów znajdujących się na planszy, co pozwala im na zwiększanie swojej populacji. Symulacja zwraca na koniec liczbę pszczół i szerszeni. Może się tak zdarzyć, że na planszy pozostaną same pszczoły, co będzie oznaczało wygraną pszczół.

Język, w którym został wykonany program: Java

Opis symulacji:

Łąka jest kwadratową planszą o zadanej długości boku. Na planszy znajdują się dwa rodzaje kwiatów – każdy rodzaj przechowuje inną ilość nektaru. Dla planszy o polu równym n, każdego rodzaju kwiatów jest pierwiastek z n. Rodzaje kwiatów (lawenda oraz krokus) dziedziczą po klasie ogólnej Kwiat, zawierającej wszelkie zmienne. Symulacja w sposób losowy umieszcza kwiaty na planszy z zastrzeżeniem, że jedno pole może być zajęte przez maksymalnie jeden obiekt.

Użytkownik na początku działania symulacja zadaje ilość pszczół oraz szerszeni – są to obiekty, które poruszają się po planszy oraz wchodzą w interakcje z innymi obiektami. Program sprawdza poprawność zadanych liczb, poprzez sprawdzenie, czy liczba nie jest ujemna lub zbyt duża do rozmiaru planszy. Program tworzy podaną ilość obiektów typu pszczoła i szerszeń (które dziedziczą po klasie Owad) oraz losowo umieszcza je na planszy, ponownie jedno miejsce na planszy może być zajęte przez maksymalnie jeden z tych dwóch rodzajów obiektów (rozumie się przez to, że na jednym polu planszy jednocześnie może znajdować się obiekt typu kwiat oraz obiekt typu owad, jednak nie mogą się znajdować dwa obiekty typu owad lub dwa obiekty typu kwiat).

Program na środku planszy umieszcza obiekt typu Ul, którego zadaniem będzie tworzenie nowych pszczół po spełnieniu zadanych kryteriów.

Po początkowym stworzeniu oraz ustawieniu podanych obiektów symulacja rozpoczyna się. W pierwszej fazie po kolei odbywa się ruch po planszy każdej pszczoły, następnie ruch każdego szerszenia. Następnie faza jest powtarzana.

Ruch pszczoły rozpoczyna się od ewentualnego zebrania nektaru jeśli jest na polu, na którym znajduje się kwiat z niezerową ilością nektaru. Następnie zmienia swoje położenie na położenie ula, w którym zostawia zebrany nektar i wraca na swoją poprzednią pozycję, co kończy jej ruch. Jeśli pszczoła nie może zebrać nektaru wykonuje ruch – zostają wylosowane jej nowe współrzędne w zależności od szybkości jej poruszania. Po wylosowaniu przemieszcza się ona, a następnie sprawdza swoje otoczenie i zlicza ilość pszczół oraz szerszeni znajdujących się wokół niej. Jeśli wokół pszczoły znajduje się szerszeń dochodzi do walki pomiędzy obiektami. Jeśli wokół szerszenia znajduję się więcej niż jedna pszczoła przegrywa on, a tym samym obiekt typu szerszeń zostaje usunięty. Jeśli wokół szerszenia znajduje się tylko jedna pszczoła, to szerszeń wygrywa walkę, tym samym obiekt typu pszczoła zostaje usunięty. Walka lub brak obiektów wokół pszczoły po przemieszczeniu się kończy jej ruch. Ruch szerszenia polega na wylosowaniu nowych współrzędnych, przemieszczeniu się, sprawdzeniu otoczenia wokół oraz ewentualnej walki na podstawie danych z otoczenia. Po każdym ruchu program zlicza obecną ilość szerszeni oraz obecną ilość pszczół, a następnie zapisuje je do pliku txt.

Obiekt Ul gromadzi nektar, aby przy odpowiedniej jego ilości móc stworzyć nowy obiekt typu pszczoła oraz umieścić go na planszy. Po stworzeniu obiektu nektar w ulu się zeruje, a obiekt ponownie zaczyna go gromadzić.

Symulacja kończy się w momencie, kiedy obiektów danego rodzaju (pszczoła lub szerszeń) jest zero. Program zwraca informacje, który gatunek wygrał oraz jaka jest jego liczebność.

Wyświetlanie: Program w konsoli informuje o zmianach w obiektach, takich jak usunięcie szerszenia, usunięcie pszczoły, czy powstanie nowej pszczoły. Na koniec w konsoli wyświetlana jest informacja o zwycięstwie jednej populacji oraz jej liczebność. Dodatkowo program uruchamia prostą aplikację okienkową, w której na bieżąco (dzięki uśpieniu programu w odpowiednich momentach) wyświetlany jest aktualny stan planszy oraz ilość pszczół i szerszeni.
